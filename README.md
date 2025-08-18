```mermaid
flowchart TD
    A[camera] --> B[EdgeGateway(GPU/TPU server)]
    B --> C[AutoML Vision 모델]
    C --> D[실시간 불량 검출]
