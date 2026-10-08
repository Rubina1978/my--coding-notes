## to check with heroku if something is wrong:

# heroku access to CLI and use in terminal

- heroku login
- go on page and sign in 
- then heroku apps
- type app-name
- then heroku run python manage.py shell -a YOUR-APP-NAME

- will get >>> prompt
- then if image issue with displaying do this:
- then run 
```bash
from django.conf import settings
print(settings.STORAGES)
print(settings.MEDIA_URL)
print(settings.MEDIA_ROOT)

from home_page.models import Project

p = Project.objects.first()

print(image.name)
print(image.url)
```
