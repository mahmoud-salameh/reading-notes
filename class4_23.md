# Django Custom User

Django ships with a built-in User model for authentication and if you'd like a basic tutorial on how to implement log in, log out, sign up and so on see the Django Login and Logout tutorial for more.

## Setup

To start, create a new Django project from the command line. We need to do several things:
* create and navigate into a dedicated directory called accounts for our code
* install Django
* make a new Django project called config
* make a new app accounts
* start the local web server

## AbstractUser vs AbstractBaseUser
There are two modern ways to create a custom user model in Django: AbstractUser and AbstractBaseUser.

## Custom User Model

Creating our initial custom user model requires four steps:

* update config/settings.py
* create a new CustomUser model
* create new UserCreation and UserChangeForm
* update the admin

## Superuser

It's helpful to create a superuser that we can use to log in to the admin and test out log in/log out. On the command line type the following command and go through the prompts.

## DjangoX

### Installation

DjangoX can be installed via Pip, Pipenv, or Docker depending upon your setup. To start, clone the repo to your local computer and change into the proper directory.

    git clone https://github.com/wsvincent/djangox.git
    cd djangox

#### Pip

    python3 -m venv djangox
    $ source djangox/bin/activate
    (djangox) $ pip install -r requirements.txt
    (djangox) $ python manage.py migrate
    (djangox) $ python manage.py createsuperuser
    (djangox) $ python manage.py runserver

#### Pipenv

    $ pipenv install
    $ pipenv shell
    (djangox) $ python manage.py migrate
    (djangox) $ python manage.py createsuperuser
    (djangox) $ python manage.py runserver

#### Docker

    $ docker build .
    $ docker-compose up -d
    $ docker-compose exec web python manage.py migrate
    $ docker-compose exec web python manage.py createsuperuser

    
### Setup

### # Run Migrations
(djangox) $ python manage.py migrate

# Create a Superuser
(djangox) $ python manage.py createsuperuser

# Confirm everything is working:
(djangox) $ python manage.py runserver

# Load the site at http://127.0.0.1:8000

