```mermaid
flowchart TD

    %% Input stage
    A[Production Line Camera] --> B[Edge Gateway GPU/TPU Server]

    %% Edge Inference
    B --> C[AutoML Vision Model Vertex AI Edge Deployment]
    C --> D[Real-time Defect Detection ms-level Response]

    %% Edge Processing Results
    D --> E1[On-site Alarm/PLC Control Defective Item Removal]
    D --> E2[Local Log DB Storage]

    %% Cloud Integration
    E2 --> F[Google Cloud IoT Core RETIRED from Edge / PubSub HTTPS MQTT]
    F --> G[Vertex AI Monitoring / Dify Workflow]

    %% Team Collaboration
    G --> H1[Quality Manager Dashboard]
    G --> H2[Automated Report Generation]
    G --> H3[Teams/Slack Notifications]

    %% Grouping
    subgraph Edge["Factory Floor On-Premise"]
        A --> B --> C --> D
        D --> E1
        D --> E2
    end

    subgraph Cloud["Google Cloud"]
        F --> G
    end

    subgraph Collaboration["Team Collaboration"]
        G --> H1
        G --> H2
        G --> H3
    end
