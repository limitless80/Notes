Sure! Here’s a complete guide to set up Login and Signup pages in Django, including CSS and static file configurations.

### 1. **Set Up Django Project and App**

Assuming you have a Django project and an app created, we'll use the app named `users` for this example. If not, create them using:

```bash
django-admin startproject myproject
cd myproject
python manage.py startapp users
```

### 2. **Update `settings.py`**

**`settings.py`**:
1. **Add `users` to `INSTALLED_APPS`**:
   ```python
   INSTALLED_APPS = [
       ...
       'users',
   ]
   ```

2. **Configure Static Files**:
   ```python
   STATIC_URL = '/static/'
   STATICFILES_DIRS = [
       BASE_DIR / 'static',
   ]
   ```

### 3. **Create Views for Login and Signup**

**`users/views.py`**:
```python
from django.shortcuts import render, redirect
from django.contrib.auth import authenticate, login as auth_login
from django.contrib.auth.forms import UserCreationForm
from django.contrib.auth import logout as auth_logout
from django.contrib.auth.decorators import login_required

# Sign Up View
def signup(request):
    if request.method == 'POST':
        form = UserCreationForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('login')
    else:
        form = UserCreationForm()
    return render(request, 'users/signup.html', {'form': form})

# Login View
def login_view(request):
    if request.method == 'POST':
        username = request.POST['username']
        password = request.POST['password']
        user = authenticate(request, username=username, password=password)
        if user is not None:
            auth_login(request, user)
            return redirect('home')  # Redirect to home page after login
        else:
            return render(request, 'users/login.html', {'error': 'Invalid username or password'})
    return render(request, 'users/login.html')

# Logout View
@login_required
def logout_view(request):
    auth_logout(request)
    return redirect('login')
```

### 4. **Define URLs for Login and Signup**

**`users/urls.py`**:
```python
from django.urls import path
from .views import signup, login_view, logout_view

urlpatterns = [
    path('signup/', signup, name='signup'),
    path('login/', login_view, name='login'),
    path('logout/', logout_view, name='logout'),
]
```

**`myproject/urls.py`**:
```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('users.urls')),  # Include users app URLs
]
```

### 5. **Create HTML Templates**

**`users/templates/users/signup.html`**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sign Up</title>
    <link rel="stylesheet" href="{% static 'css/styles.css' %}">
</head>
<body>
    <header>
        <h1>Sign Up</h1>
    </header>
    <main>
        <form method="post">
            {% csrf_token %}
            {{ form.as_p }}
            <button type="submit">Sign Up</button>
        </form>
        <p>Already have an account? <a href="{% url 'login' %}">Login here</a></p>
    </main>
</body>
</html>
```

**`users/templates/users/login.html`**:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login</title>
    <link rel="stylesheet" href="{% static 'css/styles.css' %}">
</head>
<body>
    <header>
        <h1>Login</h1>
    </header>
    <main>
        <form method="post">
            {% csrf_token %}
            <div>
                <label for="username">Username:</label>
                <input type="text" id="username" name="username" required>
            </div>
            <div>
                <label for="password">Password:</label>
                <input type="password" id="password" name="password" required>
            </div>
            <button type="submit">Login</button>
        </form>
        {% if error %}
            <p style="color: red;">{{ error }}</p>
        {% endif %}
        <p>Don't have an account? <a href="{% url 'signup' %}">Sign up here</a></p>
    </main>
</body>
</html>
```

### 6. **Create CSS File**

**`static/css/styles.css`**:
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
}

header {
    background-color: #4CAF50;
    color: white;
    padding: 15px 0;
    text-align: center;
}

main {
    padding: 20px;
}

form {
    background: white;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 400px;
    margin: 0 auto;
}

form div {
    margin-bottom: 15px;
}

form label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
}

form input[type="text"], form input[type="password"] {
    width: 100%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

form button[type="submit"] {
    background-color: #4CAF50;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    font-size: 14px;
}

form button[type="submit"]:hover {
    background-color: #45a049;
}

p {
    text-align: center;
}
```

### Summary

1. **Views**: Create views for signup, login, and logout.
2. **URLs**: Define URL patterns and include them in the project’s URL configuration.
3. **Templates**: Create HTML templates for signup and login.
4. **Static Files**: Configure static files in `settings.py` and create a CSS file for styling.

Make sure to run migrations and create a superuser if needed:

```bash
python manage.py migrate
python manage.py createsuperuser
```

Start your Django server to test:

```bash
python manage.py runserver
```

Now, you should have functional login and signup pages styled with CSS.