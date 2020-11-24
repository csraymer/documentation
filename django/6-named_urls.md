# Named URLs

`In views`
```
urlpatterns = [
    path('<ind:id'>, views.detail, name="detail")
]
```

`Used in a template`
```
<a href="{% url 'detail' meeting.id %}">
    {{ meeting.title }}
</a>
```

## Template Language: For

<! - Curly braces and percent signs:
    Execute a template tag -->

`From template`
```
<ul>
    {% for m in meetings %}
        <li> Meeting id is: {{ m.id }} </li>
    {% endfor %}
</ul>
```

## Mapping URLs for Apps

`meetings/urls.py`

`- urls.py in app`

```
from django.urls import path
from .views import detail

urlpatterns = [
    path('<int:id>, detail)
]
```

`meeting_planner/urls.py`

`- project-wide urls.py`

```
from django.urls import include, path

urlpatterns = [
    path('meetings/', include('meetings.urls')),
]
```

Now all views from `meetings/urls.py` will be included in the project wide `urls.py`.

All urls from `meetings/urls` will be prefixed with `meetings/`.