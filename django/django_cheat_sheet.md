# Django Cheat Sheet

## Start a Project

Create virtual environment

```bash
python -m venv .venv
```

Activate

```bash
.venv\Scripts\activate
```

Install Django

```bash
pip install django~=5.2
```

Check Django version

```bash
python -m django --version
```

Create project

```bash
django-admin startproject new_portfolio .
```

Create requirements.txt

```bash
pip freeze > requirements.txt
```

Run the initial migrations:

```bash
python manage.py migrate
```

This creates the default Django database tables (admin, auth, sessions, contenttypes).

Start the development server:

```bash
python manage.py runserver
```
---

## Create an App

```bash
python manage.py startapp home_page
```

Remember:
- Add app to INSTALLED_APPS
- Create urls.py in the app.
- Include app URLs in the project urls.py.

---

## Templates

Project structure

templates/
    base.html
    home_page/
        home.html
        about.html
        contact.html

Remember:

settings.py

DIRS = [BASE_DIR / "templates"]

---

## Base Template

Common structure:

header

content block

footer

Pages extend base.html.

---

## Static

Remember:

{% load static %}

CSS

{% static 'css/base.css' %}

Images

{% static 'images/profile.jpg' %}





## Common Mistakes

- Forgot to add templates to DIRS.
- Forgot to add app to INSTALLED_APPS.
- Forgot {% load static %}.
- bootstrap.bundle already includes Popper.

## Requirements

Install package:

```bash
pip install 

Save installed packages:

```bash
pip freeze --local > requirements.txt