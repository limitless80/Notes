### 1. Setting Up Models

First, define your models in the `models.py` file of your Django app. Models are Python classes that map to database tables.

For example, let's assume you have an app called `myapp` and you want to create a `User` model.

**myapp/models.py:**

```python
from django.db import models

class User(models.Model):
    name = models.CharField(max_length=100)
    age = models.IntegerField()
    email = models.EmailField()

    def __str__(self):
        return self.name
```

### 2. Apply Migrations

Once you've defined your models, you need to create and apply migrations to create the corresponding database tables.

Open the terminal in Visual Studio and run the following commands:

```bash
python manage.py makemigrations myapp
python manage.py migrate
```

### 3. Adding Data

You can add data to the database in several ways. Here are a few methods:

#### Using the Django Shell

1. **Open the Django shell:**

   ```bash
   python manage.py shell
   ```

2. **Insert data using the Django ORM:**

   ```python
   from myapp.models import User

   user1 = User(name='John Doe', age=28, email='john@example.com')
   user1.save()

   user2 = User(name='Alice Smith', age=24, email='alice@example.com')
   user2.save()
   ```

#### Using Django Admin

1. **Create a superuser (if you haven't already):**

   ```bash
   python manage.py createsuperuser
   ```

2. **Register your model in the admin site:**

   **myapp/admin.py:**

   ```python
   from django.contrib import admin
   from .models import User

   admin.site.register(User)
   ```

3. **Run the development server:**

   ```bash
   python manage.py runserver
   ```

4. **Log in to the admin site** at `http://127.0.0.1:8000/admin/` using your superuser credentials and add data through the web interface.

#### Using a Django View

You can also add data through a Django view. Create a view that adds data to the database and map it to a URL.

**myapp/views.py:**

```python
from django.shortcuts import render
from .models import User

def add_user(request):
    if request.method == 'POST':
        name = request.POST.get('name')
        age = request.POST.get('age')
        email = request.POST.get('email')

        user = User(name=name, age=age, email=email)
        user.save()

        return render(request, 'user_added.html')

    return render(request, 'add_user.html')
```

**myapp/urls.py:**

```python
from django.urls import path
from . import views

urlpatterns = [
    path('add_user/', views.add_user, name='add_user'),
]
```

**Templates:**

- **add_user.html:**

  ```html
  <form method="POST">
      {% csrf_token %}
      <label for="name">Name:</label>
      <input type="text" id="name" name="name"><br><br>

      <label for="age">Age:</label>
      <input type="text" id="age" name="age"><br><br>

      <label for="email">Email:</label>
      <input type="email" id="email" name="email"><br><br>

      <input type="submit" value="Add User">
  </form>
  ```

- **user_added.html:**

  ```html
  <p>User added successfully!</p>
  ```

### Running the Server

After setting up the view and templates, run the development server:

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000/add_user/` to add a new user.

These are the common methods to insert data into an SQLite database using Django. Choose the method that best fits your needs. Let me know if you need any further assistance!
```
BASE_DIR = Path(__file__).resolve().parent.parent

STATIC_URL = '/static/'

STATICFILES_DIRS = [

    os.path.join(BASE_DIR, 'main/static'),

]

STATIC_ROOT = os.path.join(BASE_DIR, 'staticfiles')

MEDIA_URL = '/media/'

MEDIA_ROOT = BASE_DIR / 'media'
```