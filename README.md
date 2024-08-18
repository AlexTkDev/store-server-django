
# Store Server

This project is a Django-based study project aimed at developing a server for a store application. It includes features such as product management, user authentication, and background task processing.

## Stack

- [Python](https://www.python.org/downloads/): Programming language used for the project.
- [Django](https://www.djangoproject.com/): Web framework for building the server-side application.
- [PostgreSQL](https://www.postgresql.org/): Relational database management system used for data storage.
- [Redis](https://redis.io/): In-memory data structure store used for caching and task queue.

## Features

- **User Authentication**: Secure user login and registration.
- **Product Management**: CRUD operations for products.
- **Background Tasks**: Asynchronous task processing with Celery.
- **Caching**: Efficient data retrieval with Redis caching.

## Local Development

To set up the project locally, follow these steps:

### 1. Set Up Virtual Environment

Create and activate a virtual environment to manage project dependencies:

```bash
python3.9 -m venv ../venv
source ../venv/bin/activate
```

### 2. Install Dependencies

Upgrade `pip` and install the required packages:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 3. Database Setup

Run migrations to set up the database schema:

```bash
./manage.py migrate
```

Load initial data into the database (replace `<path_to_fixture_files>` with the path to your fixture files):

```bash
./manage.py loaddata <path_to_fixture_files>
```

Start the Django development server:

```bash
./manage.py runserver
```

### 4. Run Redis Server

Start the Redis server for caching and background task management:

```bash
redis-server
```

### 5. Run Celery Worker

Start the Celery worker for processing background tasks:

```bash
celery -A store worker --loglevel=INFO
```

## Configuration

### Settings

The configuration of the project is located in `store/settings.py`. Here you can adjust database settings, secret keys, and other project-specific configurations.

### Environment Variables

Ensure the following environment variables are set:

- `DATABASE_URL`: URL for PostgreSQL database connection.
- `REDIS_URL`: URL for Redis server connection.
- `SECRET_KEY`: Django secret key for cryptographic operations.

### Fixtures

Fixture files are located in the `store/fixtures/` directory. These files are used to load initial data into the database.

## Testing

To run tests, use the following command:

```bash
./manage.py test
```

Ensure all tests pass before deploying changes.

## Deployment

For deploying the project to a production environment, follow the deployment instructions in the `DEPLOYMENT.md` file.

## Contributing

Contributions are welcome! Please follow the standard pull request workflow:

1. Fork the repository.
2. Create a new branch for your changes.
3. Commit your changes with descriptive messages.
4. Push your branch to your forked repository.
5. Create a pull request to merge your changes into the main repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to adjust or expand upon these sections based on the specifics of your project and any additional details you want to include.
