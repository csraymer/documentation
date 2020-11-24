# Model Template View

## View
- Behavior
- Python functions
- Mapped to URL

## Template
- Presentation
- Generates HTML

## Model
- Data
- Model classes
- Mapped to DB table

## Retrieving Model Data

Model classes have a .objects attribute that let you retrieve data.

- Get all objects
    - `meetings = Meeting.objects.all()`

- Get object count
    - `num_meetings = Meeting.objects.count()`

- Get a specific object
    - `meeting = Meeting.objects.get(pk=5)`

## Get or 404

```
from django.shortcuts import get_object_or_404

from .models import Meeting

def detail(request, id):

    meeting = get_object_or_404(Meeting, pk=id)
```

## Parameters in URLS

```
urlpatterns = [
    path('/example/<int:x>', my_view)
]
```

<int:x> will match a number in the url. 

This number will be assigned to the view parameter `x`

`/example/5` : x will be 5

If URL contains no number: 404