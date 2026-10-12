# Network and firewall

| Port | Side | Purpose |
|---|---|---|
| 2000 | console | network install (Awoo protocol); SSM connects, console then pulls from SSM |
| 2002 | PC (SSM) | web server: `/list.json`, console inventory, save upload |
| 2003 | console (SSI) | HTTP control server |

Allow inbound TCP 2002 for SSM in the Windows firewall (private networks). The console must keep SSI open;
if it slept, wake it and reopen SSI.
