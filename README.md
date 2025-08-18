```mermaid
flowchart TD
    A[camera] --> B[Edge Gateway(GPU/TPU server)]
    B --> C[AutoML Vision model]
    C --> D[Inspection]
