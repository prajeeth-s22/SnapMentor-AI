# SnapMentor AI

Private, on-device voice and optional vision interview coaching for Snapdragon-powered HP PCs.

## Submission Positioning

**Challenge target:** Snapdragon-powered HP PCs  
**Primary use case:** Campus placement / technical interview preparation  
**Core value:** Voice-first practice + local AI evaluation + measurable progress

## Architecture

```text
Microphone ──> Whisper ASR ──> Transcript ──> Llama 3.2 Instruct ──> Structured Feedback
                                              ^
Webcam ──> Pose model (optional) ────────────|
                                              |
Resume / Role Profile ────────────────────────┘
                                              |
                                    Local SQLite / JSON
                                              |
                                    Progress Dashboard
```

## Proposed AI Components

- Whisper model from Qualcomm AI Hub for speech recognition.
- Quantized Llama 3.2 Instruct from Qualcomm AI Hub for local answer evaluation.
- Optional pose-estimation model from Qualcomm AI Hub for presentation cues.
- ONNX Runtime / Qualcomm AI Runtime / QNN path as validated on the target Snapdragon device.

## Important

Do not claim benchmark numbers until they are measured on the actual target Snapdragon-powered HP PC.

Record:
- model version
- runtime version
- target device
- inference latency
- first-load time
- peak memory
- NPU/CPU execution information
- transcript quality
- end-to-end response time

## Suggested Repository Structure

```text
snapmentor-ai/
├── app/
│   ├── frontend/
│   └── backend/
├── models/
│   ├── manifests/
│   └── README.md
├── inference/
│   ├── asr/
│   ├── llm/
│   └── vision/
├── evaluation/
│   ├── benchmark.py
│   └── prompts.json
├── tests/
├── screenshots/
├── docs/
├── requirements.txt
├── README.md
└── LICENSE
```

## Demo Flow

1. Select Software Engineer.
2. Start mock interview.
3. Ask candidate a technical question.
4. Record answer.
5. Transcribe locally.
6. Evaluate with structured JSON rubric.
7. Display feedback and next practice recommendation.
8. Repeat and compare progress.

## Evaluation Rubric

### Technical Implementation
- Real AI Hub model integration
- Snapdragon-compatible runtime
- Working end-to-end pipeline
- Profiling and tests

### Application Use Case & Innovation
- Placement-focused workflow
- Private local inference
- Multimodal coaching
- Evidence-based feedback

### Deployment & Accessibility
- Windows 11
- Snapdragon-powered HP PC
- Offline-first core
- Typed-answer fallback
- Captions/transcript
- Keyboard-friendly controls

### Presentation & Documentation
- Architecture diagram
- Setup guide
- Model/license attribution
- Screenshots
- Benchmark evidence
- Demo instructions

## References

- Qualcomm AI Hub: https://aihub.qualcomm.com/compute
- Whisper-Base: https://aihub.qualcomm.com/models/whisper_base
- Llama 3.2 3B Instruct: https://aihub.qualcomm.com/compute/models/llama_v3_2_3b_instruct
- MediaPipe Pose: https://aihub.qualcomm.com/compute/models/mediapipe_pose
- Qualcomm Snapdragon X Elite: https://www.qualcomm.com/laptops/products/snapdragon-x-elite
