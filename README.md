```mermaid
flowchart TD
    A[생산라인 카메라] --> B[EdgeGateway(GPU/TPU 서버)]
    B --> C[AutoML Vision 모델]
    C --> D[실시간 불량 검출]
