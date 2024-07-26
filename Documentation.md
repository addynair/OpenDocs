# Documentation for Django Todo List

## Overview

The Django Todo List application is a simple task management tool that allows users to create, view, update, and delete their tasks. It leverages Django's powerful web framework features to provide a user-friendly interface for managing to-do items.

## Functionality

### Models

#### Task

- **`Task.objects.create(title, completed)`**
  - Creates a new task with the specified title and completion status.
- **`Task.objects.all()`**

  - Retrieves all tasks from the database.

- **`Task.objects.filter(completed=True)`**

  - Returns a queryset of all completed tasks.

- **`Task.objects.get(pk)`**

  - Retrieves a task by its primary key (ID).

- **`Task.save()`**

  - Saves the current instance of the task to the database.

- **`Task.delete()`**
  - Deletes the current instance of the task from the database.

### Views

#### TaskListView

- **`get_queryset()`**
  - Returns all tasks for display on the task list page.
- **`get_context_data(**kwargs)`\*\*
  - Adds additional context (like form data) to the template context.

#### TaskDetailView

- **`get_object()`**

  - Retrieves a specific task based on the provided primary key.

- **`get_context_data(**kwargs)`\*\*
  - Provides the task detail context to the template.

#### TaskCreateView

- **`form_valid(form)`**

  - Called when the submitted form is valid. It creates a new task and redirects to the task list.

- **`form_invalid(form)`**
  - Called when the submitted form is invalid, rendering the form with error messages.

#### TaskUpdateView

- **`get_object()`**

  - Retrieves the existing task to be updated.

- **`form_valid(form)`**
  - Saves the updated task instance when the form is valid and redirects to the task detail view.

#### TaskDeleteView

- **`get_object()`**

  - Retrieves the task to be deleted based on the primary key.

- **`post()`**
  - Handles the post request to delete the task and redirect to the task list.

### Forms

#### TaskForm

- **`clean()`**

  - Validates the form data and raises validation errors if any required fields are missing.

- **`save(commit=True)`**
  - Saves the form data as a Task instance, optionally committing to the database.

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

```
