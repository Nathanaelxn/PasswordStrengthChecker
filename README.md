# Password Strength Checker

A small Django mini project. Type a password and see its strength live.

## Run it

```bash
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py runserver
```

Open http://127.0.0.1:8000/

## How it works

- `checker/utils.py` scores a password using an entropy estimate, with penalties
  for common passwords, repeated characters and keyboard/alphabet sequences.
- `checker/views.py` exposes `POST /api/check/` returning JSON.
- `checker/static/checker/app.js` calls it as you type (debounced).
- No database; passwords are never stored or logged.
