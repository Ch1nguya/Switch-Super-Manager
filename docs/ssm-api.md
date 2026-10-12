# SSM HTTP API (PC, port 2002)

| Method | Path | Purpose |
|---|---|---|
| GET | `/list.json` | library listing (used by the console installer) |
| GET | `/api/console` | last known console inventory |
| POST | `/api/console/inventory` | console pushes its inventory (see [console-inventory.md](console-inventory.md)) |
| POST | `/api/console/save?title=&name=` | tar body of a save, stored as zip |
| POST | `/api/console/save-result` | result of a backup |
| POST | `/api/console/ack`, `/api/console/event` | progress and events from SSI |
