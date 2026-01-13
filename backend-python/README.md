# backend-python 🐍

## Overview

A small FastAPI app used for demonstration. The application exposes a single GET route `/` that returns a JSON greeting and, by default, runs on `http://localhost:8000` using Uvicorn.

## Prerequisites 🔧

- Python 3.12+ installed (verify with `python --version`)
- Recommended: create a virtual environment for local development
- Optional: `pip`-based tooling or `poetry` for dependency management

## Project layout 📁

- `main.py` — FastAPI application
- `pyproject.toml` — project metadata / dependencies
- `routers/` — additional route modules (if added)

## Setup & install

From the `backend-python/` folder:

```bash
# create and activate a virtual environment (macOS/Linux)
python -m venv .venv
source .venv/bin/activate

# upgrade pip and install runtime deps
pip install -U pip
pip install fastapi uvicorn

# alternatively install via pyproject tooling (poetry/pip)
# e.g., with pip: pip install -e .  (if you add a proper setup)
```

If you add a `requirements.txt` file, use `pip install -r requirements.txt`.

## Run (development)

```bash
# from backend-python/
uvicorn main:app --reload --host 0.0.0.0 --port 8000
# or run directly--main.py contains a uvicorn run call
python main.py
```

Service URL: `http://localhost:8000`

Quick check:

```bash
curl http://localhost:8000/
```

## Tests 🧪

There are no tests included by default. Add tests (pytest recommended) and run:

```bash
pytest
```

## Docker (optional)

A simple Dockerfile example you can add:

```Dockerfile
FROM python:3.11-slim
WORKDIR /app
COPY pyproject.toml .
# install build deps if required and runtime deps
RUN pip install --no-cache-dir fastapi uvicorn
COPY . .
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
```

## Troubleshooting & tips ⚠️

- Ensure you activated the virtualenv before installing or running the app.
- If the port is in use, pass a different `--port` to `uvicorn`.

---

## Contributing

Please add tests and update this README when you change the API surface or add dependencies.

---

License: MIT
