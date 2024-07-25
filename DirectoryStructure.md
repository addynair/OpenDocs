# Directory Structure of Django Todo List

## Overview
This document provides a detailed look at the directory structure of the Django Todo List project.

### Root Directory
- **`manage.py`**: A command-line utility for managing the Django project.

### `django_todolist/`
- **`__init__.py`**: Marks this directory as a Python package.
- **`models.py`**: Defines the `Task` model with fields for the task's title, description, and completion status.
- **`views.py`**: Contains views for handling tasks, including listing, creating, updating, and deleting tasks.
- **`urls.py`**: Maps URL patterns to views for routing requests.
- **`forms.py`**: Includes forms for creating and updating tasks.

### `templates/`
- **`base.html`**: Base template for the application, providing a common layout for other templates.
- **`task_list.html`**: Template for displaying the list of tasks.
- **`task_form.html`**: Template for creating and editing tasks.

### `static/`
- **`styles.css`**: Contains CSS styles used throughout the application.

### `migrations/`
- **Migration Files**: Manage database schema changes for the `Task` model.

### `requirements.txt`
Lists the Python packages required for the project.


