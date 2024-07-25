# OpenDocs
This repository serves as an example for Task-07. The repository used for this example is the [Django Todo List](https://github.com/bradtraversy/django-todolist) application.

## Django Todo List

### Overview
Django Todo List is a simple to-do list application built with Django. It allows users to manage tasks, including creating, updating, and deleting items. This project serves as a practical introduction to Django and demonstrates basic CRUD (Create, Read, Update, Delete) operations.

### Features
- Create, update, and delete tasks
- View a list of tasks
- Mark tasks as completed or pending

### Setup Instructions
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/bradtraversy/django-todolist.git
   cd django-todolist

2. **Create a Virtual Environment:**
   ```python -m venv env
	source env/bin/activate

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt

4. **Apply Migrations:**
   ```bash
   python manage.py migrate

5. **Run the Development Server:**
   ```bash
   python manage.py runserver

6. Navigate to http://127.0.0.1:8000/ to access the application.

### Usage
- **Create Task:** Navigate to the task creation page, enter task details, and submit.
- **Update Task:** Edit existing tasks by navigating to the task update page.
- **Delete Task:** Remove tasks from the list using the delete option.

### Contribution Guidelines
- **Reporting Issues:** Please report any issues or bugs using the GitHub Issues tab.
- **Submitting Pull Requests:** Fork the repository, make your changes, and submit a pull request with a description of your changes.



