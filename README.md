# Grass Desktop & Mobile Clients

  Node.js clients for managing multiple Grass accounts and devices, with desktop and mobile identities, networkpoints farming,
  proxy routing, and traffic reporting for bandwidth usage analisys (bonus scripts)

  ## Two Clients

   Script                      Configuration           Purpose
  ━━━━━━━━━━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━━━  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
   grass_desktop.js           accounts_desktop.json   Desktop client based on Windows executable analysis
  ──────────────────────────  ──────────────────────  ───────────────────────────────────────────────────────────────
   grass_mobile.js            accounts_mobile.json    Mobile-oriented client developed from native-library analysis

  Both currently start through H2, with WebSocket implementations retained in the code.

  ## Access

  This is a paid private script.

  For licensing or access inquiries, contact:

  **Telegram:** https://t.me/roodrigato

  ## Features

  - Accounts and devices without a fixed script limit. Run multiple profiles and devices from JSON configuration. Actual
    capacity depends on memory, bandwidth, available connections, and service limits.

  - Per-device proxies. Assign separate proxy connections to individual devices.
  - Device registration and identity persistence. Generate or reuse signing credentials, register devices, and preserve
    identities across restarts.

  - Signed check-in. Support for device-authenticated director requests using Ed25519 signatures.
  - H2 CONNECT tunnels. Forward destination traffic bidirectionally, with backpressure handling to control buffering.
  - HTTP request handling. Execute and deliver server-requested webcrawl operations.

  - Device-specific user agents. Load device identity settings from account configuration.
  - Automatic reconnection. Recover from connection failures with reconnect scheduling.
  - Registration-aware startup. Apply startup delays to devices needing registration; registered devices start
    immediately.

  - Configurable traffic policies by proxy username. Control selected CONNECT requests through initial allowances, probability settings,
    and timed allowances.

  - Traffic logging. Record connection activity and transferred kilobytes. Desktop metadata is grouped by profile, date,
    proxy, and URL, with batched persistence.

  - Graceful shutdown. Cancel pending startup timers and close active connections.

  ## Proxy Configuration

  Residential/ISP proxies are the intended setup for proxied devices. Proxy compatibility and service acceptance are not
  guaranteed merely by using a residential IP.

  Routing includes configured direct-connection exceptions, so not every destination necessarily uses the assigned
  proxy.

  - A proxy URL assigns that proxy to the device.
  - "empty" enables direct mode.
  - Null or blank proxy entries skip the device.

  ## Version Updates

  The scripts have been updated across successive client releases through binary analysis and protocol comparisons.
  Updates are applied manually as changes are identified; there is no automatic guarantee of compatibility with future
  releases.

  ## Run

  Install the project dependencies, configure the relevant accounts file, then start a client:

  node grass_desktop.js

  node grass_mobile.js

  Keep account files, tokens, private keys, and proxy credentials out of the public repository.

  Unofficial implementation. Not affiliated with or endorsed by Grass.
