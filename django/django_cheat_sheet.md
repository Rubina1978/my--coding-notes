# Django Cheat Sheet

## Start a Project

## Create virtual environment

```bash
python -m venv .venv
```

Activate

```bash
.venv\Scripts\activate
```

## Install Django

```bash
pip install django~=5.2
```

## Check Django version

```bash
python -m django --version
```

## Create project

```bash
django-admin startproject new_portfolio .
```

## Create requirements.txt

```bash
pip freeze > requirements.txt
```

## Run the initial migrations:

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

## the flow of an app:

create app -> add to installed apps in settings.py -> create models -> register in admin.py -> makemigrations + migrate -> create views -> create template -> create urls

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
```

## Models → Database → Admin

## 1. Create the model

In `models.py`:

```bash
from django.db import models


class Project(models.Model):
    title = models.CharField(max_length=100)
    description = models.TextField()

```
To make a field optional:

```bash

blank=True
```

## Create fixtures before moving databases!

```bash 

python manage.py dumpdata home_page --indent 4 > home_page/fixtures/home_page.json

```

## upload fixtures to project back

```bash
python manage.py loaddata home_page/fixtures/home_page.json 
## Check before making migrations
## just change the page if different project or page
```bash

python manage.py make migrations --dry

```
## check before migrate

```bash

python manage.py migrate --plan

## make migrations 

```bash
python manage.py makemigrations
python manage.py migrate
```

## Register model in the app's admin.py

```bash
from django.contrib import admin
from .models import Project

admin.site.register(Project)
```
### create superuser(if needed):
```bash
python manage.py createsuperuser

go to /admin/ and log in
```

### 🧠 Tiny memory trick

Think:

**"I designed it → I told Django → Django built it → I made it editable."**

- **Model** = design what you store
- **makemigrations** = tell Django what changed
- **migrate** = actually change the database
- **admin.py** = make it manageable through Admin


## connect js 

```bash

<script src="{% static 'javascript/index.js' %}"></script>

```

## to control layout with css instead of summernotes and others:

``` bash

<h1>{{ about.heading }}</h1>

{{ about.introduction|linebreaks }}

{% for fact in key_facts %}
    <div class="fact-card">
        <h3>{{ fact.title }}</h3>
        <p>{{ fact.description }}</p>
    </div>
{% endfor %}

```

