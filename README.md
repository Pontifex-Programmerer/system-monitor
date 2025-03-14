# Node.js System Monitor

This project is a system monitoring tool built using Node.js and Express. It follows the MVC architecture and provides real-time system stats (CPU, RAM, and Disk Read/Write) on a web page. It also logs errors and system events such as high CPU or RAM usage.

## Features
- Platform-independent
- Reads CPU, RAM, and Disk R/W usage
- Logs errors to an `error` folder
- Logs system events (e.g., high CPU/RAM usage) to a `syslogs` folder
- Uses MVC architecture

## Project Flowchart

```mermaid
graph TD;
    A[Start] --> B[Initialize Express App]
    B --> C[Set up Routes]
    C --> D[Start Server]

    D -->|Request to View System Stats| E[Controller: Fetch System Stats]
    E --> F[Model: Retrieve CPU, RAM, Disk Usage]
    F --> G[Return Data to Controller]
    G --> H[Send Data to View]
    H --> I[Render Web Page]

    F --> J{Check Thresholds}
    J -->|High CPU Usage| K[Log to syslogs/high_cpu.log]
    J -->|High RAM Usage| L[Log to syslogs/high_ram.log]
    
    E -->|Error Occurs| M[Log Error to error/error.log]

    style K fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style L fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style M fill:#ccccff,stroke:#0000ff,stroke-width:2px;
