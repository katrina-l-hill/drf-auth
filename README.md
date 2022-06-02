# LAB - Class 32

## Project: Django REST Framework Authentication & Production Server

### Author: Katrina Hill

- attribution to instructor JB Tellez for class demo code modified for this application

### Setup

- PORT - <http://0.0.0.0:8000/>
- DATABASE_URL - <http://0.0.0.0:8000/api/v1/food/>

### How to initialize/run the application

#### Terminal 1

- create virtual environment: python3 -venv .venv
- activate virtual environment: source .venv/bin/activate
- pip install pytest
- pip freeze > requirements.txt
- Add appropriate/applicable installed apps, allowed hosts, rest framework, static urls, admin, permissions, views, urls, and database default in respective files.

#### Terminal 2

- docker compose up
- docker-compose run web bash
- pip install django
- pip install djangorestframework
- pip install djangorestframework-simplejwt
- pip install pyscopg2-binary
- pip install gunicorn
- pip install whitenoise
- django-admin startproject <\projectname>_project .
- python manage.py runserver (click on local host IP address to ensure site set up properly)
- python manage.py migrate
- python manage.py startapp <\project app name>
- python manage.py showmigrations
- python manage.py migrate
- python manage.py createsuperuser (create a username, password, and email address)
- exit
- docker compose up or docker compose up --build
- open localhost/development server to ensure site set up properly

### Thunder Client process

- click New Request
- in dropdown, select POST
- type <http://0.0.0.0:8000/api.token/>
- click on Body, then JSON
- type in the Json Content window: {"username": "admin", "password": "admin"}
- click Send
- in the Response window, you should see the "refresh" and "access" tokens
- copy the "access" token (everything between the parentheses)
- click New Request
- in dropdown, select GET
- type <http://0.0.0.0:8000/api/v1/food>
- click on Auth, then Bearer
- paste the copied "access" token into the empty field below Bearer Token
- click Send
- In the Response window, you should see two food entries that were created in the the production server

### How to run the tests

- import class Food
- import APITestCase
- type python manage.py test

- tests were provided from instructor JB Tellez in class demo code
