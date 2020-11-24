# Adding a New App

```
python manage.py startapp appname
```

The `manage.py` script is located inside the Django project.

`cd` into the right folder before running it.

## Django Apps

- They are a Python package specifically for used in a Django project.

- Contains models, views, templates, urls.

- Most Django projects contain several apps.

- Apps can be reused between projects.

- Keep apps small and simple.

## Adding a Page

`views.py`

```
from django.http import HttpResponse

def welcome(request):
    return HttpResponse("Welcome!")
```

To view the HTTP response above, we need to assign it a URL:

`urls.py`

```
from website.views import welcome

urlpatterns = [
    path('', welcome),
    ...
]
```
