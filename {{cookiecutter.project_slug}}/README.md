# {{cookiecutter.project_name}}

> Template [boilerplate code](https://appseed.us/boilerplate-code) used by [AppSeed](https://appseed.us) to generate simple admin dashboards coded in Flask - Features:

<br />

{% if cookiecutter.theme == 'volt' %}
- UI Kit: **Volt Dashboard** (Lite Version) Bootstrap 5 design provided by **Themesberg**
{% endif %}
{% if cookiecutter.theme == 'soft-ui' %}
- UI Kit: **Soft UI Dashboard** (Free Version) Bootstrap 5 design provided by **[Creative-Tim](https://bit.ly/3fKQZaL)**
{% endif %}
{% if cookiecutter.theme == 'datta-able' %}
- UI Kit: **Datta Able** (Free Version) design provided by **[CodedThemes](https://bit.ly/37fF9RT)**
{% endif %} 
{% if cookiecutter.theme == 'material-dashboard' %}
- UI Kit: **Material Dashboard** (Free Version) Bootstrap 5 design provided by **[Creative-Tim](https://bit.ly/3fKQZaL)**
{% endif %}
{% if cookiecutter.theme == 'star-admin' %}
- UI Kit: **Star Admin 2** (Free Version) by **[BootstrapDash](https://bit.ly/2UTgih5)**
{% endif %}

- Up-to-date [dependencies](./requirements.txt): **Flask 2.0.1**
- [SCSS compilation](#recompile-css) via **Gulp**
- DBMS: SQLite, PostgreSQL (production) 
- DB Tools: SQLAlchemy ORM, Flask-Migrate (schema migrations)
- Modular design with **Blueprints**
- Session-Based authentication (via **flask_login**), Forms validation
- Deployment scripts: Docker, Gunicorn / Nginx, HEROKU
- Support via **Github** (issues tracker) and [Discord](https://discord.gg/fZC6hup).

<br />

> Links

{% if cookiecutter.theme == 'volt' %}
- [Flask Bootstrap 5 Volt](https://appseed.us/admin-dashboards/flask-dashboard-volt) - product page
- [Flask Bootstrap 5 Volt](https://flask-volt-dashboard.appseed-srv1.com/) - LIVE deployment
{% endif %} 
{% if cookiecutter.theme == 'soft-ui' %}
- [Flask Soft UI Dashboard](https://appseed.us/product/flask-soft-ui-dashboard) - product page
- [Flask Soft UI Dashboard](https://flask-soft-ui-dashboard.appseed-srv1.com/) - LIVE Demo
{% endif %}
{% if cookiecutter.theme == 'datta-able' %}
- [Datta Able Flask](https://appseed.us/admin-dashboards/flask-datta-able) - product page
- [Datta Able Flask](https://flask-datta-able.appseed-srv1.com/) - LIVE deployment
{% endif %} 
{% if cookiecutter.theme == 'material-dashboard' %}
- [Flask Dashboard Material](https://appseed.us/admin-dashboards/flask-dashboard-material-design) - product page
- [Flask Dashboard Material](https://flask-material-dashboard.appseed-srv1.com/) - LIVE deployment
{% endif %} 
{% if cookiecutter.theme == 'star-admin' %}
- [Star Admin Flask](https://appseed.us/admin-dashboards/flask-star-admin) - product page
- [Star Admin Flask](https://flask-star-admin.appseed-srv1.com/) - LIVE deployment
{% endif %} 

<br />

## Quick Start in [Docker](https://www.docker.com/)

> Change the directory inside the source code.

```bash
$ cd <GENERATED_CODE>
```

> Start the app in Docker

```bash
$ docker-compose up --build  
```

Visit `http://localhost:85` in your browser. The app should be up & running.

<br />

{% if cookiecutter.theme == 'volt' %}
![Flask Bootstrap 5 Volt - Template project provided by AppSeed.](https://raw.githubusercontent.com/app-generator/flask-dashboard-volt/master/media/flask-dashboard-volt-intro.gif)
{% endif %} 
{% if cookiecutter.theme == 'soft-ui' %}
![Soft UI Dashboard - Flask Template project provided by AppSeed.](https://raw.githubusercontent.com/app-generator/flask-soft-ui-dashboard/master/media/flask-soft-ui-dashboard-screen.png)
{% endif %}
{% if cookiecutter.theme == 'datta-able' %}
![Flask Datta Able - Open-source seed project, GIF animated presentation.](https://user-images.githubusercontent.com/51070104/140760187-9b851237-4e58-496b-be79-e6b73f0f0ab4.gif)
{% endif %} 
{% if cookiecutter.theme == 'material-dashboard' %}
![Flask Dashboard Material Design - Template project provided by AppSeed.](https://user-images.githubusercontent.com/51070104/138474101-7a46215e-daa8-489d-b811-19eb1c3ce4da.gif)
{% endif %} 
{% if cookiecutter.theme == 'star-admin' %}
![Flask Star Admin - Seed provided by AppSeed.](https://user-images.githubusercontent.com/51070104/142849749-130c06e2-9ebc-4c48-84c7-d35fe1ae26b3.gif)
{% endif %} 

<br />

## How to use it

Change the directory inside the source code.

```bash
$ # Get the code
$ cd <GENERATED_SOURCES>
$
$ # Virtualenv modules installation (Unix based systems)
$ virtualenv env
$ source env/bin/activate
$
$ # Virtualenv modules installation (Windows based systems)
$ # virtualenv env
$ # .\env\Scripts\activate
$
$ # Install modules - SQLite Database
$ pip3 install -r requirements.txt
$
$ # OR with PostgreSQL connector
$ # pip install -r requirements-pgsql.txt
$
$ # Set the FLASK_APP environment variable
$ (Unix/Mac) export FLASK_APP=run.py
$ (Windows) set FLASK_APP=run.py
$ (Powershell) $env:FLASK_APP = ".\run.py"
$
$ # Set up the DEBUG environment
$ # (Unix/Mac) export FLASK_ENV=development
$ # (Windows) set FLASK_ENV=development
$ # (Powershell) $env:FLASK_ENV = "development"
$
$ # Start the application (development mode)
$ # --host=0.0.0.0 - expose the app on all network interfaces (default 127.0.0.1)
$ # --port=5000    - specify the app port (default 5000)  
$ flask run --host=0.0.0.0 --port=5000
$
$ # Access the dashboard in browser: http://127.0.0.1:5000/
```

> Note: To use the app, please access the registration page and create a new user. After authentication, the app will unlock the private pages.

<br />

## Code-base structure

The project is coded using blueprints, app factory pattern, dual configuration profile (development and production) and an intuitive structure presented bellow:

> Simplified version

```bash
< PROJECT ROOT >
   |
   |-- apps/
   |    |
   |    |-- home/                          # A simple app that serve HTML files
   |    |    |-- routes.py                 # Define app routes
   |    |
   |    |-- authentication/                # Handles auth routes (login and register)
   |    |    |-- routes.py                 # Define authentication routes  
   |    |    |-- models.py                 # Defines models  
   |    |    |-- forms.py                  # Define auth forms (login and register) 
   |    |
   |    |-- static/
   |    |    |-- <css, JS, images>         # CSS files, Javascripts files
   |    |
   |    |-- templates/                     # Templates used to render pages
   |    |    |-- includes/                 # HTML chunks and components
   |    |    |    |-- navigation.html      # Top menu component
   |    |    |    |-- sidebar.html         # Sidebar component
   |    |    |    |-- footer.html          # App Footer
   |    |    |    |-- scripts.html         # Scripts common to all pages
   |    |    |
   |    |    |-- layouts/                   # Master pages
   |    |    |    |-- base-fullscreen.html  # Used by Authentication pages
   |    |    |    |-- base.html             # Used by common pages
   |    |    |
   |    |    |-- accounts/                  # Authentication pages
   |    |    |    |-- login.html            # Login page
   |    |    |    |-- register.html         # Register page
   |    |    |
   |    |    |-- home/                      # UI Kit Pages
   |    |         |-- index.html            # Index page
   |    |         |-- 404-page.html         # 404 page
   |    |         |-- *.html                # All other pages
   |    |    
   |  config.py                             # Set up the app
   |    __init__.py                         # Initialize the app
   |
   |-- requirements.txt                     # Development modules - SQLite storage
   |
   |-- Dockerfile                           # Deployment
   |-- docker-compose.yml                   # Deployment
   |-- gunicorn-cfg.py                      # Deployment   
   |-- nginx                                # Deployment
   |    |-- appseed-app.conf                # Deployment 
   |
   |-- .env                                 # Inject Configuration via Environment
   |-- run.py                               # Start the app - WSGI gateway
   |
   |-- ************************************************************************
```

<br />

> The bootstrap flow

- `run.py` loads the `.env` file
- Initialize the app using the specified profile: *Debug* or *Production*
  - If env.DEBUG is set to *True* the SQLite storage is used
  - If env.DEBUG is set to *False* the specified DB driver is used (MySql, PostgreSQL)
- Call the app factory method `create_app` defined in app/__init__.py
- Redirect the guest users to Login page
- Unlock the pages served by *home* blueprint for authenticated users

<br />

## Recompile CSS

To recompile SCSS files, follow this setup:

<br />

**Step #1** - Install tools

- [NodeJS](https://nodejs.org/en/) 12.x or higher
- [Gulp](https://gulpjs.com/) - globally 
    - `npm install -g gulp-cli`
- [Yarn](https://yarnpkg.com/) (optional) 

<br />

**Step #2** - Change the working directory to `assets` folder

```bash
$ cd apps/static/assets
```

<br />

**Step #3** - Install modules (this will create a classic `node_modules` directory)

```bash
$ npm install
// OR
$ yarn
```

<br />

**Step #4** - Edit & Recompile SCSS files 

```bash
$ gulp scss
```

The generated file is saved in `static/assets/css` directory.

<br />

## Deployment

The app is provided with a basic configuration to be executed in [Docker](https://www.docker.com/), [Heroku](https://www.heroku.com/), [Gunicorn](https://gunicorn.org/), and [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/).


### [Heroku](https://www.heroku.com/)
---

Steps to deploy on **Heroku**

- [Create a FREE account](https://signup.heroku.com/) on Heroku platform
- [Install the Heroku CLI](https://devcenter.heroku.com/articles/getting-started-with-python#set-up) that match your OS: Mac, Unix or Windows
- Open a terminal window and authenticate via `heroku login` command
- Clone the sources and push the project for LIVE deployment

```bash
$ cd <GENERATED_SOURCES>
$
$ # Check Heroku CLI is installed
$ heroku -v
heroku/7.25.0 win32-x64 node-v12.13.0 # <-- All good
$
$ # Check Heroku CLI is installed
$ heroku login
$ # this commaond will open a browser window - click the login button (in browser)
$
$ # Create the Heroku project
$ heroku create
$
$ # Trigger the LIVE deploy
$ git push heroku master
$
$ # Open the LIVE app in browser
$ heroku open
```

<br />

### [Gunicorn](https://gunicorn.org/)
---

Gunicorn 'Green Unicorn' is a Python WSGI HTTP Server for UNIX.

> Install using pip

```bash
$ pip install gunicorn
```
> Start the app using gunicorn binary

```bash
$ gunicorn --bind 0.0.0.0:8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

### [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
---

Waitress (Gunicorn equivalent for Windows) is meant to be a production-quality pure-Python WSGI server with very acceptable performance. It has no dependencies except ones that live in the Python standard library.

> Install using pip

```bash
$ pip install waitress
```
> Start the app using [waitress-serve](https://docs.pylonsproject.org/projects/waitress/en/stable/runner.html)

```bash
$ waitress-serve --port=8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

## Credits & Links

- [Flask Framework](https://www.palletsprojects.com/p/flask/) - The offcial website
- [Boilerplate Code](https://appseed.us/boilerplate-code) - Index provided by **AppSeed**
- [Boilerplate Code](https://github.com/app-generator/boilerplate-code) - Index published on Github

<br />

---
{{cookiecutter.project_name}} - Provided by **AppSeed** [App Generator](https://appseed.us/app-generator).
