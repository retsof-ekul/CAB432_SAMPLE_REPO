# TeamUp

Repository for group T166's IFB398 + IFB399 IT capstone project

## Prerequisites

| Tool | Version |
|------|---------|
| Python | 3.13 |
| Node.js | 20+ |
| UV (recommended) | latest |

## Running Locally

Both services must be running at the same time.
API requires environment variable JWT_SECRET to be set.

### Backend (FastAPI)

#### Development Mode
```bash
cd backend
uv sync
uv run fastapi dev src/main.py
```
API runs at **http://localhost:8000**
Interactive docs available at http://localhost:8000/docs

#### Production/Container Mode
```bash
cd backend
uv sync --frozen --no-dev  # Uses uv.lock for exact dependency versions
uvicorn src.main:app --host 0.0.0.0 --port 8000
```
For Docker deployment, see backend/Dockerfile which uses uv for dependency installation and symlinks database to /data/app.db

### Frontend (SvelteKit)
*Frontend instructions to be added once frontend code location is confirmed*

## Seeding Test Data

The following script seeds the API database with test data:

```bash
cd backend
uv run python -m scripts.seed
```
Multiple runs of the script will add further test units, users, and groups

## Environment Variables

- `JWT_SECRET`: Secret key for JWT token signing (required)
- `DATABASE_PATH`: Optional path for SQLite database file (defaults to app.db in backend directory)

## Dependency Management

This project uses **uv** for fast dependency resolution:
- `pyproject.toml` defines project dependencies
- `uv.lock` ensures reproducible builds
- Run `uv sync` to install dependencies
- Run `uv sync --frozen --no-dev` for production installs

## Project Structure

- `backend/src/main.py`: FastAPI application entry point
- `backend/src/routers/`: API route modules (auth, users, groups, units, etc.)
- `backend/src/models/`: SQLAlchemy ORM models
- `backend/src/constants.py`: Application constants and enums
- `backend/src/database.py`: Database connection and session management
- `backend/Dockerfile`: Production container build instructions using uv