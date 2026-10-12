# Console inventory (SSI → SSM)

SSI (Switch Super Installer) reports what is installed on the console to Switch Super Manager (SSM).
SSM keeps the latest snapshot in `cache/console_inventory.json` and uses it for the **Console** tab.

## Transport

| | |
|---|---|
| Endpoint | `POST http://<pc>:2002/api/console/inventory` (the same address SSI already uses for `list.json`) |
| Body | JSON, `Content-Type: application/json`, UTF-8, at most 8 MiB, `Content-Length` required |
| When | each time SSI opens (or enters *Install via SSM*), and after an install finishes |
| Read back | `GET http://<pc>:2002/api/console` returns the stored snapshot (debugging) |

Responses are JSON: `200 {"ok": true, "titles": N}`, `400` bad payload, `409` the MAC does not match the
console configured in SSM (the snapshot is ignored), `411/413` missing or oversized body.

The PC address of the console is taken from the connection itself: SSI does not need to send its IP.
When the payload carries a MAC, SSM stores it and keeps the *Console IP* setting in sync with the address
the POST came from (this is what follows the console when its Wi-Fi IP changes).

## Format (`schema` = 1)

```json
{
  "schema": 1,
  "console": {
    "mac": "AA:BB:CC:DD:EE:FF",
    "name": "Living room Switch",
    "firmware": "19.0.1",
    "ssi_version": "1.2.0"
  },
  "storage": {
    "sd":   { "total": 256000000000, "free": 120000000000 },
    "nand": { "total": 25769803776,  "free": 9000000000 }
  },
  "titles": [
    { "id": "0100000000010000", "type": "base",   "storage": "sd",   "version": 0,     "size": 1073741824 },
    { "id": "0100000000010800", "type": "update", "storage": "sd",   "version": 65536, "size": 52428800 },
    { "id": "0100000000011001", "type": "dlc",    "storage": "nand", "version": 0,     "size": 10485760,
      "name": "Optional DLC name" }
  ]
}
```

| Field | Notes |
|---|---|
| `schema` | must be `1` |
| `console.mac` | Wi-Fi MAC, any of `AA:BB:CC:DD:EE:FF`, `AA-BB-…`, `AABBCCDDEEFF`; optional but needed for IP tracking |
| `console.name`, `firmware`, `ssi_version` | optional, informational |
| `storage.<sd|nand>` | bytes: `total` capacity and `free` space of the volume (`nand` = the user partition) |
| `titles[].id` | 16 hex digits (title ID of the application, patch or add-on content) |
| `titles[].type` | `base` (application), `update` (patch), `dlc` (add-on content) |
| `titles[].storage` | `sd` or `nand`: where the content is installed |
| `titles[].version` | integer version from the content meta key (e.g. `65536` = v1) |
| `titles[].size` | bytes taken by all the contents of that title on that storage |
| `titles[].name` | optional; SSM resolves names from TitleDB when absent (keeps the payload small) |

Rules applied by SSM: entries with a bad ID/type/storage are skipped, a `(id, storage)` pair is kept once,
sizes and versions are clamped to non-negative integers, at most 20 000 titles.
`received_at` (server clock) and `peer_ip` are added to the stored snapshot; the console clock is not trusted.

## Getting the data on the console (libnx)

[JKSV](https://github.com/J-D-K/JKSV) is a good model for enumerating titles: it lists applications with
`nsListApplicationRecord` and reads names/icons with `nsGetApplicationControlData`. For the inventory SSI
needs the installed *contents* too, so per storage (`NcmStorageId_SdCard`, `NcmStorageId_BuiltInUser`):

1. `ncmOpenContentMetaDatabase` + `ncmContentMetaDatabaseList` (types `Application`, `Patch`, `AddOnContent`)
   gives the content meta keys: ID, version and type.
2. For each key, `ncmContentMetaDatabaseListContentInfo` lists its contents; add up
   `ncmContentInfoSizeToU64(&info, &size)` to get `size`.
3. Capacity: `nsGetTotalSpaceSize(storage)` / `nsGetFreeSpaceSize(storage)`, or `fsFsGetTotalSpace` /
   `fsFsGetFreeSpace` on `sdmc:/` and the user partition (SSI already shows these two numbers).
4. MAC: `setcalInitialize()` + `setcalGetWirelessLanMacAddress(&mac)` (libnx `set:cal`); firmware: `setsysGetFirmwareVersion`.

Send the JSON with the libcurl already used by SSI (`POST`, `Content-Type: application/json`).

## Testing without a console

```
python tools/simulate_console.py --host 127.0.0.1 --titles 40
```
