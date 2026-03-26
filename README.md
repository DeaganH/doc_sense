# Living Soils – Soil Report Analysis and Community Learning

Living Soils is a Django 4.x application for uploading soil report PDFs, sending them for asynchronous analysis via an LLM API, and presenting the returned report data inside a user dashboard. The platform is designed to support both practical soil report interpretation and community learning around soil health, student feedback, and shared understanding of results. Target platform: PythonAnywhere.

## Getting Started

1. **Python**: 3.11 (PythonAnywhere system image that supports Django 4.x).
2. **Install deps**: `pip install -r requirements.txt`
3. **Env vars**: copy `.env.example` to `.env` and fill values.
4. **Migrate**: `python manage.py migrate`
5. **Run dev server**: `python manage.py runserver`
6. **Start worker (Django-Q)**: `python manage.py qcluster`

## Key Apps

- `presentations`: upload handling, async processing, LLM API calls, and report data views.
- `dashboard`: account pages, soil report views, soil sample tracking, student records, and community feedback workflows.

## What The Platform Supports

- Uploading soil report PDFs for automated analysis.
- Displaying returned report data in the Living Soils dashboard.
- Tracking supporting information such as soil samples and student records.
- Encouraging community learning through feedback and shared interpretation of soil health information.

## Deployment (PythonAnywhere summary)

- Add a **Virtualenv** with project deps.
- Set `DJANGO_SETTINGS_MODULE=config.settings.production`.
- Point WSGI file to `config/wsgi.py`.
- Collect static: `python manage.py collectstatic --noinput`.
- Run DB migrations.
- Start `qcluster` as a PythonAnywhere **always-on task**.

## Directories

- `config/`: project settings, URLs, ASGI/WSGI.
- `presentations/`: upload, processing, retry, delete, and report data display logic.
- `dashboard/`: logged-in dashboard experience and soil learning workflows.
- `templates/`, `static/`, `media/`: user-facing assets and uploads.

## Tests

Add tests under `presentations/tests/` (not scaffolded yet).
