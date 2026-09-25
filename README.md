# CodeAlpha Task 2 - Event Registration System

Backend Development internship project using Django and SQLite.

## Features
- Django backend
- Event model and user registration model
- API to view event list and event details
- API to register users for events
- Prevents duplicate registrations
- Checks event capacity
- API to view registrations
- Django Admin panel

## Run on Windows

Open Command Prompt inside this project folder:

```bat
python -m pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py shell -c "from events.models import Event; from django.utils import timezone; Event.objects.get_or_create(name='Python Workshop', defaults={'description':'Backend development workshop','date':timezone.now(),'location':'Online','capacity':50})"
python manage.py runserver
```

Open:

http://127.0.0.1:8000/

Admin:

http://127.0.0.1:8000/admin/

## API endpoints

GET `/api/events/`

GET `/api/events/1/`

POST `/api/register/`

Example JSON:
```json
{
  "username": "student1",
  "email": "student1@example.com",
  "event_id": 1
}
```

GET `/api/registrations/`
