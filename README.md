# Django project code a CRM app tutorial

## Install Python and update PIP
> PowerShell
* Install [Python 3.12.0](https://www.python.org/downloads/release/python-3120/)
* Check Python version: `python --version`
* Install and upgrade PIP: `python -m pip install --upgrade pip`

## Configure the virtual environment
> PowerShell
* Allow execute scripts to activate a virtual environment: `Set-ExecutionPolicy RemoteSigned -Scope CurrentUser`
* Install the virtual environment package: `pip3 install virtualenv`
* Access the repository folder: `cd .\cd django-project-code-a-crm-app-tutorial\`
* Create a virtual environment: `python -m virtualenv venv`
* Activate the virtual environment: `.\venv\Scripts\activate`
* Install the libraries required: `pip3 install -r requirements.txt`

## How to run the app
> PowerShell
* Access the repository folder: `cd .\cd django-project-code-a-crm-app-tutorial\`
* Activate the virtual environment: `.\venv\Scripts\activate`
* Run the app: `python manage.py runserver`
* Deactivate the virtual environment: `deactivate`

## Configure MySQL database
> Windows
* Go to the link and install MySQL Community edition: 
[MySQL Community Downloads] (https://dev.mysql.com/downloads/installer/)
* In the Environment Variables window, under the System variables section, find and select the Path variable, then click Edit. In the Edit Environment Variable window, click New, then add the path to the MySQL installation’s bin directory. For example, if MySQL is installed in C:\Program Files\MySQL\MySQL Server X.0\, add this path:
`C:\Program Files\MySQL\MySQL Server X.0\bin`
* Verify the configuration opening CMD and type:
`mysql --version`

## Change authentication plugin of MySQL
* If exist a problem with `caching_sha2_password`, you can switch the MySQL user's authentication plugin from caching_sha2_password to mysql_native_password. 

* Log in to MySQL via the command line:
`mysql -u root -p`

* Change the authentication plugin for the user that is giving you trouble. Replace your_user and your_password with your MySQL username and password:
`ALTER USER 'your_user'@'localhost' IDENTIFIED WITH mysql_native_password BY 'your_password'`

* Apply the changes:
`FLUSH PRIVILEGES;`

* Add the auth_plugin parameter to your connection call, like this:
import mysql.connector
```
connection = mysql.connector.connect(
    host="localhost",
    user="your_user",
    password="your_password",
    database="your_database",
    auth_plugin="mysql_native_password"
)
```

## Project configuration
* (instructions):
`django-admin startproject dcrm`
* (instructions):
`cd dcrm`
* (instructions):
`python manage.py startapp website`
* In settings.py add 'website,' in INSTALLED_APPS:
```
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'website',
]
```
* In settings.py edit DATABASES like this:
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'elderco',
        'USER': 'root',
        'PASSWORD': 's60iY7bN4*',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```
* (instructions):
`touch mydb.py`
`python touch mydb.py`

* (instructions):
`python manage.py migrate`

* (instructions):
`python manage.py createsuperuser`
