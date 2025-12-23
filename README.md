# final-report

# 시스템 아키텍처

아래는 프로젝트의 시스템 아키텍처 다이어그램입니다.

```mermaid
flowchart TD
    U[사용자 / 응시자] --> C[웹캠]
    C --> B[웹 브라우저]

    subgraph FE[Front-End]
        FE1[CSS]
        FE2[JavaScript]
        UI[영상 처리 영역<br/>감지 알림 · 경고 · 자세 분석]
        FE1 --> UI
        FE2 --> UI
    end

    B --> UI

    UI -->|영상 스트림 / 데이터| BE

    subgraph BE[Back-End]
        DJ[Django Framework]
        PY[Python]
        OC[OpenCV]

        subgraph AI[AI / Vision Models]
            YO[YOLO]
            MP[MediaPipe]
            PT[PyTorch]
        end

        DJ --> PY
        PY --> OC
        PY --> AI
        PT --> YO
    end

    BE -->|분석 결과| UI

```

