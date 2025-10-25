# FastAPI Calculator — Module 8

[![CI/CD](https://github.com/arhamidrees63/assignment8/actions/workflows/test.yml/badge.svg)](https://github.com/arhamidrees63/assignment8/actions)

**Docker Hub image:** `https://hub.docker.com/r/arhamidrees63/601_module8'

A FastAPI-based calculator with:
- Arithmetic ops (add, subtract, multiply, divide) via REST endpoints
- Web UI for quick testing
- Unit, integration, and Playwright E2E tests
- Dockerfile + Docker Compose
- GitHub Actions CI (tests + security scan)

---

## Quickstart (local)

```bash
git clone git@github.com:arhamidrees63/assignment8.git
cd assignment8
python3 -m venv venv
source venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
python -m playwright install --with-deps
uvicorn main:app --reload
Open: http://localhost:8000

Run tests
bash
Copy code
pytest -v
pytest --cov=app --cov-report=term-missing --cov-fail-under=90
Docker
Build & run (Compose)
bash
Copy code
docker compose up --build
Open: http://localhost:8000
Stop:

bash
Copy code
docker compose down
Pull image from Docker Hub
bash
Copy code
docker pull arhamidrees63/601_module8:latest
docker run -p 8000:8000 arhamidrees63/601_module8:latest
API (examples)
POST /add → { "a": 10, "b": 5 } ⇒ { "result": 15 }

POST /subtract → { "a": 10, "b": 5 } ⇒ { "result": 5 }

POST /multiply → { "a": 10, "b": 5 } ⇒ { "result": 50 }

POST /divide → { "a": 10, "b": 0 } ⇒ { "error": "Cannot divide by zero!" }

CI/CD
GitHub Actions workflow:

Installs dependencies (incl. Playwright browsers)

Runs unit + integration + E2E tests

Runs Trivy security scan on the built image
.
