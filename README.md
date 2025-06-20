# ALX Travel App

A Django-based travel application with REST API support and comprehensive documentation.

## Project Overview

ALX Travel App is a robust travel management system built with Django and Django REST Framework. The application provides a secure and scalable backend for managing travel listings and related functionalities.

## Features

- RESTful API architecture
- MySQL database integration
- API documentation with Swagger/OpenAPI
- Cross-Origin Resource Sharing (CORS) support
- Celery integration for background tasks
- Secure environment variable management

## Tech Stack

- Python 3.12
- Django 5.0.0
- Django REST Framework 3.14.0
- MySQL
- Celery
- RabbitMQ (Message Broker)
- Swagger/OpenAPI (drf-yasg)

## Prerequisites

- Python 3.12+
- MySQL
- RabbitMQ Server
- Required system packages:
  ```bash
  sudo apt-get update
  sudo apt-get install -y python3-dev default-libmysqlclient-dev build-essential pkg-config
  ```

## Project Setup Guide

1. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

2. Install required packages:
   ```bash
   pip install -r requirements.txt
   ```

3. Create a `.env` file in the project root:
   ```env
   DEBUG=True
   SECRET_KEY=your-secret-key
   DATABASE_URL=mysql://user:password@localhost:3306/alxtravelapp
   ALLOWED_HOSTS=localhost,127.0.0.1
   CORS_ALLOWED_ORIGINS=http://localhost:3000,http://127.0.0.1:3000
   ```

4. Configure the database:
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Create a superuser:
   ```bash
   python manage.py createsuperuser
   ```

6. Run the development server:
   ```bash
   python manage.py runserver
   ```

## Project Structure

```
alxtravelapp/
├── alxtravelapp/          # Project configuration directory
│   ├── __init__.py
│   ├── settings.py        # Project settings
│   ├── urls.py           # Main URL configuration
│   └── wsgi.py           # WSGI configuration
├── listings/             # Main application directory
│   ├── __init__.py
│   ├── admin.py         # Admin interface configuration
│   ├── apps.py         # App configuration
│   ├── models.py       # Database models
│   ├── serializers.py  # API serializers
│   ├── urls.py        # App URL configuration
│   └── views.py       # API views
├── .env                # Environment variables
├── .gitignore         # Git ignore file
├── manage.py          # Django management script
└── requirements.txt   # Project dependencies
```

## API Documentation

The API documentation is available at:
- Swagger UI: `http://localhost:8000/swagger/`
- ReDoc: `http://localhost:8000/redoc/`

## Development Setup Commands

Here are the exact commands used to set up this project:

```bash
# Create project directory and virtual environment
mkdir alxtravelapp
cd alxtravelapp
python -m venv .venv
source .venv/bin/activate

# Install required packages
pip install Django==5.0.0 djangorestframework==3.14.0 django-cors-headers==4.3.1 \
    drf-yasg==1.21.7 celery==5.3.6 django-environ==0.11.2 mysqlclient==2.2.1 \
    python-dotenv==1.0.0

# Create Django project and app
django-admin startproject alxtravelapp .
python manage.py startapp listings

# Install system dependencies for MySQL
sudo apt-get update
sudo apt-get install -y python3-dev default-libmysqlclient-dev build-essential pkg-config

# Create database
mysql -u root -p
CREATE DATABASE alxtravelapp;
exit

# Apply migrations
python manage.py makemigrations
python manage.py migrate
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details

## Contact

Your Name - your.email@example.com
Project Link: [https://github.com/yourusername/alxtravelapp](https://github.com/yourusername/alxtravelapp)
