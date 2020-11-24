# Django Template Inheritance

```
<!-- Include all HTML from the parent template
    (This should be the first tag!) -->
{% extends "base.html" %}

{% block title %}Page Title{% endblock %}

{% block block_name %}

    This replaces the content of the block with the same name.

{% endblock %}
```

## Static Files

```
{% load static %}

<!DOCTYPE html>
<html lang="en">
<head>
    <link rel="stylesheet" 
    href="{% static 'website/style.css' %}">
```