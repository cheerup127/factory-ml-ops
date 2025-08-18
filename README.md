```mermaid
flowchart TD
    A[camera] --> B[Edge GatewayGPU/TPU server 서버]
    B --> C[AutoML Vision model]
    C --> D[Inspection]
