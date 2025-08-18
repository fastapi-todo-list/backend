# Todo Backend

FastAPI + SQLAlchemy backend for the Todo project. Serves REST endpoints and connects to Postgres.

## Requirements
- Python 3.9+

## Local development (optional)
Create and activate a virtual environment, install deps, and run uvicorn.
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```
Backend will run on http://127.0.0.1:8000

## Environment
Copy `.env.example` to `.env` and adjust if needed.
- POSTGRES_USER
- POSTGRES_PASSWORD
- POSTGRES_DB
- DB_HOST (defaults to `db` in Docker)
- DB_PORT (defaults to `5432`)
- DATABASE_URL (optional; overrides the above)

## Docker
This service is intended to be run via the Compose file in `devops/docker-compose.yml`.
From that folder:
```bash
docker compose up -d --build
```

## Endpoints
- `POST /todos/` { title: string }
- `GET /todos/`

## Notes
- The Docker image runs `uvicorn main:app` because the `app` folder is copied into `/app`.
- CORS is configured for the frontend dev server on ports 3001.
