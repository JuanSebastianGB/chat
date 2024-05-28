# Real-Time Chat Application

This application is a real-time chat application built using Django and Django Channels. It allows users to communicate instantly through a web interface, leveraging WebSockets for real-time communication.

## Features

- Real-time messaging using WebSockets
- User authentication and session management
- Scalable architecture with Django Channels and Redis

## Prerequisites

Before you begin, ensure you have the following installed on your machine:

- Python 3.8+
- Django 3.1+
- Docker
- Redis

## Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Clone the Repository

```bash
git clone https://github.com/JuanSebastianGB/chat.git
```

```bash
cd chat
```

### Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # On Windows use `venv\Scripts\activate`  `
```

### Install Dependencies

```bash

pip install -r requirements.txt`
```

### Start Redis

Ensure Redis is running. You can use Docker to run Redis:

```bash
docker run --rm -p 6379:6379 redis:7`
```

### Configure Django Settings

Make sure your Django settings are properly configured for Channels and Redis. Here's an example configuration:

```python

# settings.py

INSTALLED_APPS = [
...
'channels',
'your_app_name',
]

ASGI_APPLICATION = 'your_project_name.asgi.application'

CHANNEL_LAYERS = {
'default': {
'BACKEND': 'channels_redis.core.RedisChannelLayer',
'CONFIG': {
"hosts": [('127.0.0.1', 6379)],
},
},
}`
```

### Migrate the Database

```bash
python manage.py migrate
```

### Create a Superuser

```bash
python manage.py createsuperuser
```

### Run the Development Server

```bash
python manage.py runserver
```

### Access the Application

Open your web browser and go to `http://127.0.0.1:8000/` to access the chat application.

## Following the Tutorial

This project follows the tutorial provided by [Django Channels Documentation](https://channels.readthedocs.io/). For detailed steps and explanations, refer to the tutorial.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](https://chatgpt.com/c/CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## Acknowledgements

- [Django](https://www.djangoproject.com/)
- [Django Channels](https://channels.readthedocs.io/)
- [Redis](https://redis.io/)
