# Channel Name:
- [Think&Code](https://www.youtube.com/channel/UCNQOWS6XCj9F5eEylIKpi9g)
- [Try2Code](https://www.youtube.com/channel/UC_Ek1zBgcUgaai3u7X8v52w)
# Django Tutorial:

----------------------------------------------------
----------------------------------------------------


## Involved Steps -

### Download Django latest version
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.
```bash
pip install django
```
### Create django project
 ```bash
 django-admin startproject <project name>
 ```

### Move to project directory

```bash
cd <project name>
```

### Start your django [server](http://localhost:8000/)

```bash
python manage.py runserver 
```
### Now open your favourite browser and type below link 

```bash
http://localhost:8000
```

> As you can see your django server is working.

### Now Make Migrate.

```bash
python manage.py migrate
```
### Create superuser for admin access.
```bash
python manage.py createsuperuser
```

> __Enter username:__<br>
> __Enter your Email Address:__<br>
> __Enter your password:__<br>
> __Enter your password again:__<br>
> __Now it's done__


### Create Your First App

```bash
python manage.py startapp <app name>
```

### Now most important things for beginners
 
- Add your app name in django settings.py
```python
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    '<app name>'
]
```
- Create __urls.py__ file in your app directory and paste below lines
```python
from django.urls import path, include

urlpatterns = [

]

```
- Now link your project with your app

```bash
urlpatterns = [
    path('', include('<app name>.urls'))
]
```
- Create a directory for template inside your project directory with name __templates__
```bash
-project
  -app
  -templates
  -manage.py
  -db.sqlite3 
```
- Add template path in django __settings.py__
```python
TEMPLATES = [
    {
        'BACKEND': 'django.template.backends.django.DjangoTemplates',
        'DIRS': [os.path.join(BASE_DIR, 'templates')],
        'APP_DIRS': True,
        'OPTIONS': {
            'context_processors': [
                'django.template.context_processors.debug',
                'django.template.context_processors.request',
                'django.contrib.auth.context_processors.auth',
                'django.contrib.messages.context_processors.messages',
            ],
        },
    },
]
```
- Create a html file __base.html__ inside your templates directory


- Open your app and paste below written code in __views.py__
```python
from django.shortcuts import render
# Create your views here.
def dashboard(request):
    return render(request, 'base.html')
```

- Open __app/urls.py__ and paste below written code
```python
from django.urls import path, include
from . import views
urlpatterns = [
    path('', views.dashboard, name='dashboard')
]
```
- Now on your browser open this [server](http://localhost:8000)
- Now you are ready for actual django task.
- Done

