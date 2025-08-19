```mermaid
flowchart TD

    subgraph Local[" Local Development"]
        A1[ 데이터 준비train/val/test 디렉토리] --> A2[ TensorFlow 모델 학습EfficientNetB0 ImageNet pretrained]
        A2 --> A3[ 모델 저장SavedModel format]
    end

    subgraph GCP[" Google Cloud"]
        B1[ Cloud Storage (GCS)<br/>모델 업로드] --> B2[ Vertex AI Model Registry<br/>모델 등록]
        B2 --> B3[ Vertex AI Endpoint 모델 배포]
        B3 --> B4[ Prediction ServiceREST / gRPC API]
    end

    subgraph User[" Client"]
        C1[ 이미지 업로드] --> C2[ API 요청 to Vertex AI]
        C2 --> B4
        B4 --> C3[ 예측 결과 반환defect / good + 확률]
    end
