%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#2496ed', 'edgeLabelBackground':'#ffffff', 'tertiaryColor': '#f4f4f4'}}}%%
graph LR
    subgraph "External World"
        AdminUser[👤 System Administrator<br/>(You)]
        BackupDest[(📦 External Backup<br/>Destination)]
    end

    subgraph "LinuxOps Lab - Production Server (Ubuntu)"
        direction TB

        subgraph "🛡️ Security Perimeter Layer"
            SSH[🔑 Hardened SSH Daemon<br/>(Key-Based Auth Only)]
            Firewall[🧱 UFW / iptables Firewall<br/>(Ports locked down)]
        end

        subgraph "⚙️ Core Operations & Fundamentals"
            RBAC[👥 User Management<br/>& RBAC Permissions]
            Systemd[🚀 Custom systemd Service<br/>(Health Monitoring App)]
            Logs[📄 Observability & Logging<br/>(journalctl & /var/log)]
        end

        subgraph "🤖 Automation & Maintenance Layer"
            Cron[⏰ Cron Scheduler]
            BashScripts[📜 Bash Automation Scripts<br/>(Backups, Log Rotation, Maintenance)]
        end
    end

    %% Connections
    AdminUser ====>|Secure Encrypted Connection| SSH
    SSH --> Firewall
    Firewall --> RBAC

    RBAC -->|Manages| Systemd
    RBAC -->|Accesses| Logs

    Systemd -.->|Writes output to| Logs

    Cron ====>|Triggers periodically| BashScripts
    BashScripts -->|Reads/Rotates| Logs
    BashScripts ---->|Periodically pushes data| BackupDest

    %% Styling
    classDef external fill:#f9f9f9,stroke:#333,stroke-width:2px,color:#333;
    classDef security fill:#ffebee,stroke:#d32f2f,stroke-width:2px,color:#d32f2f;
    classDef core fill:#e3f2fd,stroke:#1976d2,stroke-width:2px,color:#1976d2;
    classDef automation fill:#e8f5e9,stroke:#388e3c,stroke-width:2px,color:#388e3c;
    classDef container fill:#ffffff,stroke:#666,stroke-width:3px,color:#333,stroke-dasharray: 5 5;

    class AdminUser,BackupDest external;
    class SSH,Firewall security;
    class RBAC,Systemd,Logs core;
    class Cron,BashScripts automation;
    class LinuxOps Lab - Production Server (Ubuntu) container;

