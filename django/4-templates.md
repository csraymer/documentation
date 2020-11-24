# Django Templates

## Templates
- Components that display data to the user.

## Templates generate text files
- We use it to create HTML

## Templates are text files
- With placeholders for variables
- Ang logic: if, for, filters, etc.

## A Django Template Example

`template file`
```
<html><head><title>{{name}}`s Page</title></head>
<body>
    <h1>Hi I'm {{name}}!</h1>
        I'm {{age}} years old.
</body></html>
```

`{{var}}` looks up `var` in the *template context*

Other text is copied to HTML output

This creates *dynamic* HTML pages

## Calling a Template

`views.py`

```
def home(request):
    return render (request, "website/welcome.html",
        { 'name':"Bob", 'age':35})
```

`render`: pass *request* and name of template file.

Third argument: dict with data passed to the template.

Templates should be in folder /templates inside app that contains views file.

Don't forget the `return` keyword.