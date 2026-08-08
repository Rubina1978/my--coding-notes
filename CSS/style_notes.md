# Navbar

## Alighn links to right

to get all links to far right use

 <ul class="navbar-nav ms-auto">

 ## Images

 make sure to have correct directory so it is pointing to the right direction e.g. 

 STATIC_URL = '/static/'

STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')
STATICFILES_DIRS = [os.path.join(BASE_DIR, 'new_portfolio', 'static')]

## Navbar

To make navigation stick add:

```bash
fixed-top

``



