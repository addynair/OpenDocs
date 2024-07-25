# Django Todo List Documentation

## Project Overview
The Django Todo List project is a straightforward application designed for task management. Built with Django, this project illustrates fundamental concepts in web development, including models, views, and templates.

## Features
- **Task Management:** Users can add new tasks, update existing ones, and remove tasks.
- **Task Status:** Tasks can be marked as completed or pending.

## Code Documentation

### `django_todolist/`
- **`__init__.py`:** This file initializes the Django application.
- **`models.py`:** Defines the `Task` model with fields for title, description, and completion status.
- **`views.py`:** Contains views for displaying tasks, handling form submissions, and processing CRUD operations.
- **`urls.py`:** Maps URL patterns to views, enabling navigation within the application.
- **`forms.py`:** Includes forms for creating and updating tasks.

### `templates/`
- **`base.html`:** The base template providing the structure for other templates.
- **`task_list.html`:** Displays the list of tasks with options to edit or delete.
- **`task_form.html`:** Provides the form for creating and editing tasks.

### `static/`
- **`styles.css`:** Contains CSS styles for the application.

### `migrations/`
- **Migration Files:** Handle database schema changes and ensure the database structure matches the Django models.

### `manage.py`
A command-line utility that helps with various Django management tasks, such as running the development server and applying migrations.

## Implementation Details

### Task Creation
Tasks are created through a form in `task_form.html`. The form data is processed in the `create_task` view in `views.py`, which creates a new `Task` instance in the database.

### Task Listing
Tasks are listed in `task_list.html` by querying the `Task` model in the `task_list` view. The view retrieves all tasks and passes them to the template for rendering.

### Task Update
Tasks can be updated by navigating to the edit form provided by `task_form.html`. The `update_task` view handles form submissions and updates the task details in the database.

### Task Deletion
Tasks are deleted using a link or button in `task_list.html`, which triggers a request to the `delete_task` view. This view removes the task from the database.

## Code Example

Here’s a snippet from the `views.py` file showing how the task creation is handled:

```python
from django.shortcuts import render, redirect
from .forms import TaskForm
from .models import Task

def create_task(request):
    if request.method == 'POST':
        form = TaskForm(request.POST)
        if form.is_valid():
            form.save()
            return redirect('task_list')
    else:
        form = TaskForm()
    return render(request, 'task_form.html', {'form': form})

