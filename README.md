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
