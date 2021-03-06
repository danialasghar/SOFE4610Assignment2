# SOFE 4610 Assignment 2
## Group 7: Danial Asghar, Yusuf Shaik, Hamza Farhat Ali

### Project Structure
- /mysite 
    - [myapp](mysite/myapp) - This contains the bulk of the code of our API
        - [migrations](mysite/myapp/migrations)
            - 0001_initial.py - Migration file to create the SQLlite database using the provided columns; i.e. id, temperature, humidity. 
        - [templates](mysite/myapp/templates)
            - [index.html](mysite/myapp/templates/index.html) - The Index page accessible at ip:port/app which shows the Temperature and Humidity.
        - [admin.py](mysite/myapp/admin.py) - It reads metadata from your models to provide a quick, model-centric interface where trusted users can manage content on your site.
        - [apps.py](mysite/myapp/apps.py) - This file is created to help the user include any application configuration for the app. We set the name of our app in there.
        - [models.py](mysite/myapp/models.py) - Lists the database models to be used in the application. We use model: Conditions with two properties: Temperature and Humidity.
        - [serializers.py](mysite/myapp/serializers.py) - Serializers allow complex data such as querysets and model instances to be converted to native Python datatypes that can then be easily rendered into JSON, XML or other content types. We define our model and its fields in the serializer.
        - [tests.py](mysite/myapp/tests.py) - Can be used to write test cases; we did not write any tests for this application. 
        - [urls.py](mysite/myapp/urls.py) - Defines the site URL to view mapping, for our application the mysite/urls.py is used instead. 
        - [views.py](mysite/myapp/views.py) - A view function, or view for short, is a Python function that takes a Web request and returns a Web response. Our view has a definition for index which is used to retrieve the value from the Database and rendered into the index.html
    - [mysite](mysite/mysite)
        - [urls.py](mysite/mysite/urls.py) - Defines the site URL to view mapping, for us these include /app, /api and /admin
        - [settings.py](mysite/mysite/settings.py) - Contains all the website settings, including registering any applications we create, the location of our static files, database configuration details, etc. We had to edit the ALLOWED_HOSTS and set it to * so that any incoming request (nodemcu) could connect.
        - [__init__.py](mysite/mysite/__init__.py) is an empty file that instructs Python to treat this directory as a Python package.
        - [wsgi.py](mysite/mysite/wsgi.py) is used to help your Django application communicate with the webserver.
        - [asgi.py](mysite/mysite/asgi.py) is a standard for Python asynchronous web apps and servers to communicate with each other.

### Running the Django Server
- `pip install django`
- `pip install djangorestframework django-cors-headers`
- `python manage.py runserver or python manage.py runserver <your_local_ip>`
    - Using your local IP allows you to access the web app from another device. This is necessary if you are using the nodemcu to send information to the API.

