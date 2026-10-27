# Secure Web Application

A complete college major-project starter application demonstrating secure user authentication.

## Features
- Sign up and login
- Password hashing with bcrypt
- SQLite database using SQLAlchemy ORM
- CSRF protection on forms
- Secure session configuration
- Session fixation protection after login
- Server-side input validation
- Jinja autoescaping for XSS protection
- Security HTTP headers
- Logout with POST + CSRF protection
- Profile update page
- Clean responsive interface

## Project structure

```text
secure_web_application/
├── app.py
├── requirements.txt
├── README.md
├── run.bat
├── run.sh
├── static/
│   └── style.css
└── templates/
    ├── base.html
    ├── index.html
    ├── login.html
    ├── signup.html
    ├── dashboard.html
    ├── profile.html
    └── error.html
```

## Run on Windows

1. Install Python 3.10+.
2. Open Command Prompt in this folder.
3. Run:
   `python -m venv venv`
4. Activate:
   `venv\Scripts\activate`
5. Install:
   `pip install -r requirements.txt`
6. Run:
   `python app.py`
7. Open:
   `http://127.0.0.1:5000`

Or double-click `run.bat` after Python is installed.

## Run on Linux/macOS

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
```

Then open http://127.0.0.1:5000

## Database

The application automatically creates `secure_app.db` on first run.

The password is never stored as plain text. Only a bcrypt hash is stored.

## Security mapping for your project

| Requirement | Implementation |
|---|---|
| Input validation | Server-side checks in signup/profile |
| SQL Injection | SQLAlchemy parameterized ORM queries |
| XSS | Jinja autoescaping + CSP |
| CSRF | Flask-WTF CSRF tokens |
| Password security | bcrypt hashing |
| Session security | HttpOnly, SameSite, timeout, session regeneration |
| Clickjacking | X-Frame-Options: DENY |
| MIME sniffing | X-Content-Type-Options: nosniff |

## Important before deployment

- Replace `SECRET_KEY` with a long random secret stored in an environment variable.
- Enable HTTPS and set `SESSION_COOKIE_SECURE=True`.
- Do not use Flask's development server in production.
- Add a production WSGI server such as Gunicorn/waitress.
- Consider adding account lockout/rate limiting and email verification for a real deployment.

## Suggested project title

**Secure User Authentication and Web Application Protection System**
