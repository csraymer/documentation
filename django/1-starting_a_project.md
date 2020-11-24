# Starting a Django project

## Install the latest Django release

```
python -m pip install django
```
## Starting the project

```
django-admin startproject my-project-name
```

Best practice: Always install packages inside a virtual environment.

Pycharm creates an environment for you whenever starting a project.

The django-admin script is installed inside the virtual environment so it should be active when running this.

# Running the project

## Move into the project directory
```
cd my-project name
```

## Run the development server
```
python manage.py runserver
```

This runs the Django development server. 

Will reload Python code automatically.

Stop the server with `Ctrl+C`
