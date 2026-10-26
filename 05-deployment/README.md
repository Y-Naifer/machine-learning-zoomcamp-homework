# Homework 5: Deploying Machine Learning Models (ML Zoomcamp 2026)

Files come from `cohorts/2026/homework/05-deployment` of DataTalksClub/machine-learning-zoomcamp,
plus my `q3.py`.

## Setup
```bash
sha256sum pipeline.bin     # 1646bbdcd38d4f044da6b630c5b332c93a314245a8c21929011c42de51f629f1
uv sync --locked
uv run python smoke_test.py
```

## Answers
| Q | Answer | How |
| --- | --- | --- |
| 1 | `uv --version` -> 0.13.5 | setup check |
| 2 | 1.7.2 | `scikit-learn==1.7.2` in `pyproject.toml` |
| 3 | 0.533 | `uv run python q3.py` (0.5330) |
| 4 | 0.770 | `uv run uvicorn predict:app --port 9696`, then `uv run python q6_test.py` (0.7698) |
| 5 | `python:3.11.15-slim-bookworm` | first line of `Dockerfile` |
| 6 | 0.770 | `docker build -t zoomcamp-model:2026-hw5 .`, `docker run --rm -p 9696:9696 zoomcamp-model:2026-hw5`, `python3 q6_test.py` |
