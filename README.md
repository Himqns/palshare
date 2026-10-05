# PalShare

PalShare is a workshop-built social platform powered by Django. Members can
share posts, connect with other people, and keep conversations going through a
responsive web interface and a REST API.

## Features

- User registration and login
- Text and media posts, comments, likes, reactions, and sharing
- User profiles, follow connections, and profile privacy settings
- Direct messages, saved posts, and search
- Weather and AI assistant widgets (optional API keys)
- REST API with JWT authentication, request throttling, and OpenAPI documentation

## Technology

- Python and Django 5.2
- Django REST Framework with Simple JWT
- drf-spectacular for OpenAPI / Swagger documentation
- SQLite for local development

## Run locally

Use Python 3.12 for the smoothest setup. From PowerShell:

```powershell
git clone https://github.com/Himqns/palshare.git
cd palshare
py -3.12 -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

Open <http://127.0.0.1:8000/palshare/register/> to create an account, then sign
in at <http://127.0.0.1:8000/palshare/login/>.

To run the test suite:

```powershell
python manage.py test
```

## API and integrations

- API endpoints: `/api/palshare/`
- Swagger UI: <http://127.0.0.1:8000/api/schema/swagger-ui/>
- ReDoc: <http://127.0.0.1:8000/api/schema/redoc/>

The weather and AI widgets work without credentials and show an empty state.
Set `WEATHER_API_KEY` and/or `NVIDIA_API_KEY` in your environment to enable
them. Do not commit API keys. For non-local deployments, set `DJANGO_SECRET_KEY`,
`DJANGO_ALLOWED_HOSTS`, and `DJANGO_DEBUG=0` as appropriate.
