# Copilot Instructions for Mergington High School Activities API

This guide helps AI coding agents work productively in this codebase. It covers architecture, workflows, conventions, and integration points specific to this project.

## Architecture Overview
- **Framework:** FastAPI (single-file app: `src/app.py`)
- **Frontend:** Static files in `src/static/` (HTML, JS, CSS)
- **Data Model:** In-memory Python dicts for activities and students
- **API:** REST endpoints for viewing activities and signing up
- **No database or persistent storage**—all data resets on server restart

## Developer Workflows
- **Install dependencies:**
  ```bash
  pip install fastapi uvicorn
  ```
- **Run server:**
  ```bash
  python src/app.py
  ```
- **API docs:**
  - Swagger: [http://localhost:8000/docs](http://localhost:8000/docs)
  - ReDoc: [http://localhost:8000/redoc](http://localhost:8000/redoc)
- **Frontend:**
  - Static files served from `src/static/`

## Project-Specific Patterns
- **Activity sign-up:**
  - POST `/activities/{activity_name}/signup?email=student@mergington.edu`
  - Activity name and student email are unique identifiers
- **Data model:**
  - Activities: name, description, schedule, max participants, signed-up emails
  - Students: email, name, grade
- **No authentication or authorization**
- **All logic in `src/app.py`**

## Integration Points
- **External dependencies:** Only FastAPI and Uvicorn
- **No environment variables or config files required**
- **No tests or CI/CD present**

## Conventions
- **Keep all API logic in `src/app.py`**
- **Frontend assets in `src/static/`**
- **Use meaningful identifiers (activity name, student email)**
- **Follow FastAPI conventions for endpoint and response design**

## Example Usage
- To sign up a student:
  ```bash
  curl -X POST "http://localhost:8000/activities/Basketball/signup?email=student@mergington.edu"
  ```

---
For questions or unclear patterns, review `src/README.md` and `src/app.py` for examples.
