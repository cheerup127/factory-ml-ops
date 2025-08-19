```mermaid
flowchart TD

    subgraph Local[" Local Development"]
        A1[ Prepare Data train/val/test directories] --> A2[ Train TensorFlow Model EfficientNetB0 (ImageNet pretrained)]
        A2 --> A3[ Save Model SavedModel format]
    end

    subgraph GCP[" Google Cloud"]
        B1[ Upload Model to Cloud Storage GCS] --> B2[ Vertex AI Model Registry<br/>Register Model]
        B2 --> B3[ Vertex AI Endpoint Deploy Model]
        B3 --> B4[ Prediction Service REST / gRPC API]
    end

    subgraph User[" Client"]
        C1[ Upload Image] --> C2[ API Request to Vertex AI]
        C2 --> B4
        B4 --> C3[ Return Prediction Result defect / good + probability]
    end
