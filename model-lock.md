# Model Lock Decision

## Model Details
- Model ID: Qwen/Qwen2.5-1.5B-Instruct
- Quantization: fp16 (fallback)
- Launch flags: --dtype half --max-model-len 4096 --enable-auto-tool-choice --tool-call-parser hermes

## Performance
- VRAM: 11.51 GB
- Tokens/sec: 11.1

## Quality Check
- Smoke test score: 7/10
- Decision: FALLBACK to fp16

## Reasoning
AWQ failed the smoke test threshold; falling back to fp16 for reliability.
