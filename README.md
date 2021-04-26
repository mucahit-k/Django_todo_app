# Django_todo_app

- create a project directory and cd into it
``` bash
mkdir django_project
cd django_project
```
- install virtualenv with pip and create a virtual environment
``` bash
pip install virtualenv
virtualenv djangoEnv
```
- activate virtualenv
``` bash
# for mac
source djangoEnv/bin/activate
# for windows
djangoEnv\Scripts\activate.bat
```
- install django with pip and start django project
``` bash
pip install django
django-admin startproject todo_project
```
- cd into the project and run 
``` bash
cd todo_project
python manage.py migrate
python manage.py runserver
```
- create a superuser for admin area
``` bash
python manage.py createsuperuser
```
- create first app
``` bash
python manage.py startapp todo_app
```
- add the started app name("todo_app") to INSTALLED_APP in settings.py file

.

.

.

.

.

.

.

- create your database table in models.py file
``` python
class Todos(models.Model):
    title = models.CharField(max_length=100)
    description = models.TextField(max_length=1000,blank=True)
    finished = models.BooleanField(default=False)
    date = models.DateTimeField(default=datetime.now ,blank=True)

    def __str__(self):
        return self.title
```
- migrate the created table to database
``` bash
python manage.py makemigrations
python manage.py migrate
```
- add created table to admins.py file to see the database in admin panel
``` python
from .models import Todos
admin.site.register(Todos)
```


