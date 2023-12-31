
# Django Auto Permissions

Django Auto Permissions is a Django library designed to automatically generate and apply permissions for custom methods defined in Django Rest Framework viewsets. It simplifies the process of managing permissions, ensuring that each custom viewset method has its corresponding permission without manually creating them.

## Features

- **Automatic Permission Generation**: Dynamically creates permissions for custom methods within registered viewsets.
- **Easy Integration**: Seamlessly integrates with Django's existing permission framework.
- **Django Signals for Automation**: Utilizes Django signals to automate permission creation, especially after migrations.
- **Comprehensive Testing**: Well-tested to ensure reliability.
- **Simple Registration Process**: Easily register your viewsets with the library.

## Installation

Install `django_auto_permissions` via pip:

```bash
pip install django_auto_permissions
```

## Setup

After installation, add `auto_permissions` to your `INSTALLED_APPS` in Django's `settings.py`:

```python
INSTALLED_APPS = [
    # ... other installed apps ...
    'django_auto_permissions',
]
```

## Usage

### Registering Viewsets

In your viewsets file, register each viewset with its corresponding model using `ViewsetRegistrar`.

```python
# In your viewsets.py
from django_auto_permissions.registration import ViewsetRegistrar
from myapp.models import MyModel
from myapp.viewsets import MyViewSet

# Register the viewset and model
ViewsetRegistrar.register(MyViewSet, MyModel)
```

This should be done before running your Django project, ideally in a module that gets loaded on startup, such as `views.py` or `models.py`.

### Checking Generated Permissions

Once your Django project is running, the library will automatically generate and register permissions for your custom viewset methods. These permissions can be viewed and managed in the Django admin interface.

## Contributing

Contributions to `django_auto_permissions` are welcome! Please read our contributing guidelines for submitting pull requests.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For support or queries, reach out to [Your Email or Contact Information].

## Acknowledgements

- Thanks to the Django and Django Rest Framework communities for their invaluable resources.