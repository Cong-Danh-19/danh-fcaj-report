---
title: "Build the React Application"
date: 2026-07-28
weight: 8
chapter: false
pre: " <b> 5.8.1 </b> "
---

#### 5.8.1. Build the React Application

Before uploading to AWS, we need to compile our React code into static HTML, CSS, and JS files.

1. Ensure you have updated all `TODO` placeholders in `App.jsx` with your actual Cognito IDs, HTTP API URL, and WebSocket API URL.
2. Open the terminal in your code editor (like VS Code) and stop the local development server if it's running (Press `Ctrl + C`).
3. Run the following command:
```bash
npm run build
```
4. Wait a few seconds. A new folder named dist will be generated in your project directory. This folder contains your production-ready website.