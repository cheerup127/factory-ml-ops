```mermaid
flowchart TD

    %% 입력 단계
    A[📷 생산라인 카메라] --> B[💻 Edge Gateway\n(GPU/TPU 서버)]

    %% Edge Inference
    B --> C[🧠 AutoML Vision 모델\n(Vertex AI Edge 배포)]
    C --> D[⚡ 실시간 불량 검출\n(ms 단위 응답)]

    %% Edge 처리 결과
    D --> E1[🚨 현장 알람/PLC 제어\n(불량품 제거)]
    D --> E2[📊 로컬 로그 DB 저장]

    %% 클라우드 연동
    E2 --> F[🌐 Google Cloud IoT Core / PubSub]
    F --> G[☁️ Vertex AI Monitoring / Dify Workflow]

    %% 팀 협업
    G --> H1[👩‍💻 품질 관리자 대시보드]
    G --> H2[📑 리포트 자동 생성]
    G --> H3[💬 Teams/Slack 알림]

    %% 그룹화
    subgraph Edge["공장 내부 (On-Premise)"]
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

