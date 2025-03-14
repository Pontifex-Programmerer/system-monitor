# System Monitor - Node.js

This project is a system monitoring tool built using **Node.js** and **Express**, following the **MVC architecture**. It provides real-time system statistics (CPU, RAM, Disk Read/Write) and logs important system events.

## Features
- **Platform-independent**: Runs on Windows, Linux, and macOS.
- **Monitors**:
  - CPU usage
  - RAM usage
  - Disk Read/Write operations
- **Logging**:
  - Errors are stored in the `/logs/error` folder.
  - System events (e.g., high CPU/RAM usage) are logged in `/logs/syslogs`.
- **MVC Architecture**:
  - Models handle data retrieval.
  - Controllers process system stats.
  - Views render the web page.

## System Flowchart

```mermaid
graph TD;
    subgraph app.js
        A[app start] --> B[InitApp]
        B --> C[listen]
        
        C --> D[onRequest]
        C --> E[onError]
        C --> F[onSystemEvent]
        
        D --> G[renderData]
        G --> H[sendResponse]
        
        E --> I[writeLogs]
        I --> J[(store logs)]
        
        F --> I
    end
