---
title: "Deployment & Integration"
date: 2026-07-28
weight: 6
chapter: false
pre: " <b> 5.6.3 </b> "
---

### 5.6.3. Deployment & Integration

Once both APIs are created and deployed, you need to grab their endpoint URLs to connect your frontend.

1. For the **HTTP API**: Go to **Stages**, select the `default` stage, and copy the Invoke URL (It starts with `https://...`). Append `/messages` to it when pasting it into your React code.
![Integration](/images/5-Workshop/5.6-API-gateway/Screenshot13.png)

2. For the **WebSocket API**: Go to **Stages**, select the `production` stage, and copy the WebSocket URL (It starts with `wss://...`).
![Integration](/images/5-Workshop/5.6-API-gateway/Screenshot14.png)

Update your React `App.jsx` with these URLs. Your frontend is now successfully connected to the AWS Backend!

```javascript
const REST_URL = "https://.../messages";
const WSS_URL_BASE = "wss://.../production/";