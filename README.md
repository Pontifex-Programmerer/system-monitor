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
    
    E -->|Error Occurs| M[Log Error to error.log]

    style K fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style L fill:#ffcccc,stroke:#ff0000,stroke-width:2px;
    style M fill:#ccccff,stroke:#0000ff,stroke-width:2px;
