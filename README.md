# Django Database Migration from SQLite to PostgreSQL

This guide outlines the steps to migrate a Django project's SQLite database to PostgreSQL.

## Step 1: Dump SQLite Database

Use the Django management command to create a SQL dump of your SQLite database (json UTF-8 format)

```bash
python manage.py dumpdatautf8 --output data.json
```
## Step 2: Add POSTGRE Database connection
```bash
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_postgresql_database',
        'USER': 'your_postgresql_user',
        'PASSWORD': 'your_postgresql_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```
## Step 3: Django Makemigration and migrate
```bash
python manage.py makemigrations app
python manage.py migrate
```
## Step 4: Django Makemigration and migrate
