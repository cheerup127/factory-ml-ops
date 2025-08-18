```mermaid
flowchart TD
    A[camera] --> B[Edge GatewayGPU/TPU server]
    B --> C[AutoML Vision model]
    C --> D[Inspection]
