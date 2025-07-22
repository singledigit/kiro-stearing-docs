---
title: Dev Server Management
inclusion: fileMatch
fileMatchPattern: '**/*server*.*|**/*start*.*|**/*dev*.*'
---

# Development Server Management

When starting a development server:

1. Always check if a server is already running on the intended port before starting a new one
2. Use commands like `lsof -i :PORT` or `netstat -an | grep PORT` to check for existing processes
3. If a server is already running, either:
   - Use a different port explicitly with appropriate flags
   - Stop the existing server first with appropriate commands
   - Connect to the existing server instead of starting a new one

For React/Next.js/Node applications, consider adding the `-p` or `--port` flag with an alternative port if needed, or use the `--force` flag when appropriate to automatically select an alternative port.

Example:
```bash
# Check if port 3000 is in use
lsof -i :3000 || npm start
