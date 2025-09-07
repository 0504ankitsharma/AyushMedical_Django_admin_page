## Ayush Medical – Django Admin Page

A Django-based admin interface for managing patients and appointments for Ayush Medical. This repository contains a standard Django project with an app, templates, and static assets for an admin dashboard.

### Features
- **Patient management**: Add and manage patient records.
- **Appointment management**: Add appointments.
- **Responsive admin UI**: Pre-bundled CSS/JS assets in `static/`.

### Tech Stack
- **Backend**: Django (Python)
- **Database**: SQLite (default, `db.sqlite3`)
- **Frontend**: HTML templates and static assets (Bootstrap, jQuery, charts)

### Project Structure
```
PycharmProjectsAyush-Medical/
├─ AyushMedical/
│  ├─ AyushMedical/           # Project settings and URLs
│  ├─ app/                    # Core app (models, views, admin, migrations)
│  ├─ Templates/              # HTML templates (base, patients, appointments)
│  ├─ static/                 # CSS, JS, images, fonts
│  ├─ db.sqlite3              # Default SQLite DB (dev)
│  └─ manage.py               # Django management script
├─ main.py                    # (Optional) entry point script
└─ README.md
```

### Prerequisites
- Python 3.9+ recommended
- pip (Python package manager)
- Git (optional)

### Setup (Windows PowerShell)
1) Clone or open the project folder
```powershell
# If you need to clone (replace with your repo URL)
# git clone <REPO_URL>
# cd PycharmProjectsAyush-Medical
```

2) Create and activate a virtual environment
```powershell
py -m venv .venv
. .\.venv\Scripts\Activate.ps1
```

3) Install dependencies
- If you have a requirements file:
```powershell
pip install -r requirements.txt
```
- Otherwise, install Django:
```powershell
pip install django
```

4) Apply migrations and run the server
```powershell
cd AyushMedical
python manage.py migrate
python manage.py runserver
```

5) Create a superuser (to access Django admin)
```powershell
python manage.py createsuperuser
```
Then log in at `http://127.0.0.1:8000/admin/`.

### Common Commands
```powershell
# Make new migrations after changing models
python manage.py makemigrations

# Apply pending migrations
python manage.py migrate

# Run development server
python manage.py runserver

# Run tests
python manage.py test
```

### Environment Configuration
- Default settings use SQLite. For production, configure a secure database and set `DEBUG = False` in `AyushMedical/settings.py`.
- You can add environment variables using a `.env` file (if you integrate `python-dotenv` or `django-environ`).

### Static Files
- Static assets live in `AyushMedical/static/` and are referenced by templates.
- For production, set `STATIC_ROOT` and run:
```powershell
python manage.py collectstatic
```

### URLs and Templates
- Project URLs: `AyushMedical/AyushMedical/urls.py`
- Views: `AyushMedical/app/views.py`
- Templates: `AyushMedical/Templates/`

### Development Tips
- Keep virtualenv activated while working.
- Commit migrations alongside model changes.
- Avoid committing `db.sqlite3` in team environments; prefer a fresh DB per dev.

### Deployment (Quick Notes)
- Set `ALLOWED_HOSTS` in `AyushMedical/AyushMedical/settings.py`.
- Use a production server (e.g., Gunicorn/Uvicorn + Nginx) and a managed DB.
- Configure environment variables for secrets and database credentials.


### Acknowledgments
- Dashboard UI assets credit to their respective libraries included in `static/`.
