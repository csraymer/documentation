# **Saving Python objects in a database**

## Model classes are mapped to tables
- Fields are mapped to columns

## SQL is generated
- Create/change tables (migrations)
- Insert/update/delete rows (admin)

## Supported databases: 
- PostgreSQL, MariaDB, MySQL, Oracle, SQLite
- *With package: DB2, MS SQL, and more*

# **Model Classes**

`models.py`

```
from django.db import models

class Person(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
```

# **Migration Workflow**

Important: Make sure your app is in INSTALLED_APPS

Step 1: Change model code

Step 2: Generate migration script (check it!)

```
python manage.py makemigrations
```

*Optional : Show migrations*

```
python manage.py showmigrations
```

Step 3 : Run migrations

```
python manage.py migrate
```

# Registering Models with the Admin Site

`admin.py`

```
from django.contrib import admin
from .models import Meeting
admin.site.register(Meeting)
```

Don't forget to create a superuser (in the terminal)

```
python manage.py createsuperuser
```