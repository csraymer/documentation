# Form Template
```
<form method="post">
    {{ form }}
    {% csrf_token %}

    <button type="submit">Ok</button>
</form>
```

## Form View

```
MeetingForm = modelform_factory(Meeting, exclude=[])

def new(request):
form = MeetingForm()
return render(request, "meetings/new", {'form': form})
```

## Handling Form Submit

```
# in the view

if request.method == "POST":
    # this is a form submit
    # does the input validate? then process, redirect
    # if not: show form with errors
else:
    # this is the Get, show the form

# in view when method is POST
form = MeetingForm(request.POST)
if form.is_valid():
    form.save()
    return redirect("home")
return render(request, "meetings/new.html", {'form': form})
```