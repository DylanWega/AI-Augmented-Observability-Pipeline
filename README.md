# AI-Augmented-Observability-Pipeline

flowchart TD
    A[⏰ Schedule Trigger\nevery 60 seconds] --> B[🌐 HTTP GET\nMockoon via ngrok]
    B --> C{⚡ IF Node\nerror === true?}
    C -- TRUE: 500/503 -->|error detected| D[🤖 Gemini AI\nRoot Cause Analysis]
    C -- FALSE: 200 OK -->|healthy - silent pass| E[✅ No Action\nSilence = Healthy]
    D --> F[💬 Slack Webhook\n#site-alerts]

    style A fill:#0D1520,stroke:#00D4FF,color:#fff
    style B fill:#0D1520,stroke:#7C3AED,color:#fff
    style C fill:#0D1520,stroke:#F59E0B,color:#fff
    style D fill:#0D1520,stroke:#10B981,color:#fff
    style E fill:#0D1520,stroke:#10B981,color:#fff
    style F fill:#0D1520,stroke:#4A154B,color:#fff
