# Wagtail Site

A Django-based content management system built with Wagtail CMS. This project provides a solid foundation for building modern, content-rich websites with an intuitive admin interface.

## Features

- **Wagtail CMS**: Modern, flexible content management system
- **Django 4.2**: Robust web framework with built-in admin interface
- **Search Functionality**: Built-in search with pagination
- **Docker Support**: Containerized deployment with multi-stage builds
- **Static File Management**: Optimized static file serving
- **Media Management**: Image and document handling
- **Form Support**: Contact forms and user submissions
- **SEO Ready**: Meta descriptions and search-friendly URLs

## Tech Stack

- **Backend**: Django 4.2, Wagtail 6.0
- **Database**: SQLite (development), PostgreSQL/MySQL ready
- **Frontend**: HTML5, CSS3, JavaScript
- **Deployment**: Docker, Render.com ready
- **Server**: Gunicorn WSGI server

## Project Structure

```
wagtailt-site/
├── home/                   # Home page app
│   ├── models.py          # HomePage model
│   ├── templates/         # Home page templates
│   └── static/           # Home page static files
├── search/                # Search functionality
│   ├── views.py          # Search view logic
│   └── templates/        # Search templates
├── mysite/               # Main project settings
│   ├── settings/         # Django settings
│   ├── templates/        # Base templates
│   └── urls.py          # URL configuration
├── manage.py             # Django management script
├── requirements.txt      # Python dependencies
├── Dockerfile           # Docker configuration
└── render.yaml          # Render.com deployment config
```

## Installation

### Prerequisites

- Python 3.8+
- pip
- Docker (optional)

### Local Development

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd wagtailt-site
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run migrations**
   ```bash
   python manage.py migrate
   ```

5. **Create a superuser**
   ```bash
   python manage.py createsuperuser
   ```

6. **Collect static files**
   ```bash
   python manage.py collectstatic
   ```

7. **Start the development server**
   ```bash
   python manage.py runserver
   ```

8. **Access the application**
   - Website: http://localhost:8000
   - Admin: http://localhost:8000/admin

## Docker Deployment

### Build and run with Docker

```bash
# Build the Docker image
docker build -t wagtail-site .

# Run the container
docker run -p 8000:8000 wagtail-site
```

The application will be available at http://localhost:8000

## Production Deployment

### Render.com

This project includes a `render.yaml` configuration file for easy deployment on Render.com:

1. Connect your GitHub repository to Render
2. The service will automatically detect the configuration
3. Environment variables can be set in the Render dashboard

### Environment Variables

For production deployment, consider setting these environment variables:

- `SECRET_KEY`: Django secret key
- `DEBUG`: Set to `False` for production
- `DATABASE_URL`: Database connection string (for PostgreSQL/MySQL)

## Usage

### Admin Interface

Access the Wagtail admin at `/admin` to:
- Create and manage pages
- Upload images and documents
- Manage site settings
- Create user accounts
- Configure forms

### Content Management

- **Pages**: Create hierarchical page structures
- **Blog Posts**: Add rich text content with images
- **Media**: Upload and organize images and documents
- **Forms**: Create contact forms and surveys
- **Search**: Built-in search functionality for all content

### Customization

1. **Models**: Extend page models in `home/models.py`
2. **Templates**: Customize templates in the `templates/` directories
3. **Static Files**: Add CSS/JS in `static/` directories
4. **Settings**: Modify Django settings in `mysite/settings/`

## Development

### Adding New Apps

```bash
python manage.py startapp myapp
```

### Database Migrations

```bash
# Create migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate
```

### Static Files

```bash
# Collect static files for production
python manage.py collectstatic
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For questions and support:
- Check the [Wagtail Documentation](https://docs.wagtail.org/)
- Visit the [Django Documentation](https://docs.djangoproject.com/)
- Join the [Wagtail Slack Community](https://github.com/wagtail/wagtail/wiki/Slack)

## Acknowledgments

- Built with [Wagtail CMS](https://wagtail.org/)
- Powered by [Django](https://www.djangoproject.com/)
- Deployment ready with [Render](https://render.com/)
