The Image Gallery project is a user friendly web platform created using Django to provide a ptatform for storing images as image gallery which can be accessed later using APIs and uploaded to other sites such as pinterest, facebook, instagram twitter automatically. As of now it is on online web image gallery developed using django framework

#### Functionalities of the project:
* Sign In or sign up
* create and upload images
* Update, Delete and existing images
* Search function
* Image details view
* Read more details about images

## Table of Content
* [Environment](#environment)
* [Installation](#installation)
* [File Descriptions](#file-descriptions)
* [Usage](#usage)
* [Bugs](#bugs)
* [Authors](#authors)
* [License](#license)

## Environment
This project is interpreted/tested on Ubuntu 20.04 LTS using Django (version 4.2.8)

## Installation
* To get started, install python3 development tools on your virtual machine.
* `sudo apt-get update`
* `sudo apt-get install python3-pip python3-dev libpq-dev postgresql postgresql-contrib`
* Setup postgre database: `sudo -u postgres psql` (Create database, create user and grant all priviledges, alter encoding and timezone role)
* Install virtual environment and install django
* `sudo -H pip3 install --upgrade pip` then `sudo -H pip3 install virtualenv`
* Create directory and install django 
* `mkdir Gallery && cd Gallery`
* `virtualenv imagesenv`
* `source imagesenv/bin/activate`
* Install packages: `pip install django` and `pip install psycopg2`
* Create a new django project called images: `django-admin startproject images`
* `cd images` and edit settings file with Database details
* Run django app: `python manage.py makemigrations` then `python manage.py migrate`
* Create a superuser: `python manage.py createsuperuser`
* Collect static: `python manage.py collectstatic`
* Run app: `python manage.py runserver 0.0.0.0:5000`
* Start the app main: `python manage.py startapp main`

## File Descriptions
[models.py](main/models.py) - This are the base models for my project, the entry point to the project.
#### models - contains base classes used for this project
Classes in the model:
#### `Category` - This is the class containing the category information
* Basic Fields and Utility fields defined
* `def __str__(self)` - String representation of the category name, title and uniqueId
* `def get_absolute_url(self)` - get url of category detail, slug
* `def save(self, *args, **kwargs)` - Autosave function definition

#### `Image` - This is the class containing the Image information
* Basic fields, utility fields related fields (foreign key)
* `def __str__(self)` - String representation of the category title and uniqueId
* `def get_absolute_url(self)` - get url of slug
* `def save(self, *args, **kwargs)` - Autosave function definition

[urls.py](main/urls.py) - Contails urls for respective paths

[views.py](main/views.py) - Definition of the views rendered
#### views - views rendered/requested
* `def anonymous_required(function=None, redirect_url=None)` - Definition for checking if one is logged in or not to be able to access dashboard, and invoice
* `def login(request)` - Log in request
* `def home(request)` - redirect to home page
* `def index(request)` - landing page request definition
* `def categoryPage(request, slug)` - category page request
* `def about(request)` - about page request definition
* `def imageDetailPage(request, slug1, slug2)` - Image detail request
* `def logout(request)` - Logout request

## Bugs
No known bugs at this time. 

## Authors
* Felix Too - [Github](https://github.com/felixtoo48) 
* Gamaliel Adun - [Github](https://github.com/dbaba2011)
* Inuwa Baba - [Github](https://github.com/)

## License

MIT License

`Copyright (c) 2023 Felix`
  `Too`

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.:wq
