```mermaid
flowchart TD
    A[camera] --> B[EdgeGateway(GPU/TPU server)]
    B --> C[AutoML Vision model]
    C --> D[Inspection]
