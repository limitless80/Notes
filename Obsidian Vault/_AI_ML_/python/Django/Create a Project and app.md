-To check the versionn
```
$ python -m django --version  
```
-To create project directory (of name mysite)
```
$ django-admin startproject mysite
```
-To check u have created a project
```
$ python manage.py runserver
```
![](https://i.imgur.com/O21o5LF.png)
                             Click on the http link to check.
-To create your own app(of name polls)
```
$ python manage.py startapp polls
```
-once app is created make make a python file named ***urls.py*** and link that to ***views*** module     and add the path as below to the **view*** module.
```python
from django.urls import path
from . import views
urlpatterns = [
    path("web/", views.say)
]
```
-To host any html doc in view module
	-create a folder named templates in app folder.
	 - and render that to the view as shown in the below.
```python
from django.shortcuts import render
from django.http import HttpResponse

# Create your views here.
def say(request):
    return render(request, 'hlo.html')	 
```
     -In the above code hlo.html is a file stored in the templates folder
	-after following above steps add app name to the INSTALLED_APPS variable
	 in the setting.py
