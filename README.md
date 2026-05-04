# CodeCheckAI_2026

## What this project needs

- Python 3.12
- A virtual environment
- The packages in `requirements.txt`

This project can run locally with SQLite if you do not provide MySQL settings.

## First-time setup after cloning

1. Open PowerShell in the project folder.
2. Create and activate the virtual environment:

```powershell
cd "C:\Users\Anthony Planos\Documents\GitHub\CodeCheckAI_2026"
py -3.12 -m venv venv
.\venv\Scripts\Activate.ps1
```

3. Install the dependencies:

```powershell
python -m pip install -U pip setuptools wheel
python -m pip install -r requirements.txt
```

4. Create your local `.env` file by copying `.env.sample` and updating the values you need.

5. Run database migrations:

```powershell
python manage.py migrate
```

6. Start the server:

```powershell
python manage.py runserver
```

7. Open the app in your browser:

```text
http://127.0.0.1:8000/
```

## Environment variables

Use the following values in your `.env` file:

- `SECRET_KEY` - required; use a new value for each device or deployment
- `DOMAIN` - required for this project; use `localhost:8000` for local development
- `SITE_NAME` - optional; defaults to `CodeCheckAI`
- `OPENAI_API_KEY` - optional for local startup, required for AI features
- `DB_NAME` - optional; if empty, the project uses SQLite locally
- `DB_USER` - optional MySQL setting
- `DB_PASSWORD` - optional MySQL setting
- `DB_HOST` - optional MySQL setting
- `DB_PORT` - optional MySQL setting

## Switching to MySQL later

If you want to use MySQL instead of SQLite, fill in the `DB_*` values in `.env`, then run migrations again:

```powershell
python manage.py migrate
```

## Notes

- `.env` is ignored by Git and should stay on your machine.
- Commit `.env.sample` so the setup is easy to repeat on another device.
- If you change settings, restart the development server.
