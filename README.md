# ToDo-List

A simple To-Do List using Django

![image](https://user-images.githubusercontent.com/49264993/128688375-874abcd6-7597-4353-89c2-af47896b34ef.png)

# Updated To-Do List App

## Overview

This Django-based to-do application allows users to manage their tasks efficiently. Users can perform CRUD operations on the tasks. It includes features such as user authentication, task search, and integration with an external API to fetch public holidays.

## Features

### Authentication Support

This is a basic authentication as it does not provide integrity to each user, i.e todo list for all users are same. A layer of authentication is added to restrict access to the todos.

- **User Registration:** Allows new users to create an account.
- **User Login:** Provides authentication mechanisms to ensure secure access to the application.

### Search Functionality

- **Search Todo:** Added support to search through tasks in the existing implementation.
- **Search Results Page:** An HTML page that displays the search results in a user-friendly format.

### External API Integration

- **Public Holidays Endpoint:**

  - **Endpoint:** `/api/holidays/`
  - **Purpose:** Retrieves public holidays from the Calendarific API.
  - **Request Parameters:** `country` and `year` (both fields are required).
    this api provide country name in iso_3166 format, refer to https://calendarific.com/api-documentation and https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes

  - **Response:** A JSON list of holidays with details including name, description, date, and country.

- **Example Request Params:**

```
Query Parameters:
country = IN
year = 2020
```

## Setup

### Prerequisites

- Python 3.x
- Django
- Requests library (for external API calls)

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/SOliyhan/django-todo-app.git
   ```

2. **Create a Virtual Environment:**

   ```bash
   python -m venv env
   ```

3. **Activate the Virtual Environment:**

   - On Windows:
     ```bash
     env\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source env/bin/activate
     ```

4. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

5. **Apply Migrations:**

   ```bash
   python manage.py migrate
   ```

6. **Run the Development Server:**
   ```bash
   python manage.py runserver
   ```
   (Optional) If you face any issues related to settings while running the server try this:
   ```bash
   python manage.py runserver --settings=todo_app.settings
   ```

### Configuration

1. **Calendarific API Key:** Add your Calendarific API key to through:

   ```python
   CALENDARIFIC_API_KEY = 'your_api_key'
   ```

2. **Set Up Superuser:** Create a superuser for accessing the Django admin panel:
   ```bash
   python manage.py createsuperuser
   ```

## Usage

### Access the Application

- **Homepage:** Navigate to `http://localhost:8000/` to view the application.
- **Add Tasks:** Navigate to Navbar and use the Add button to add a new todo.
- **Search Tasks:** Use the Search button functionality to search from matching todos from all of the todo created by a user.
- **Public Holidays API:** Access the endpoint at `http://localhost:8000/api/holidays/` with query parameters for `country` and `year`.

### Authentication

- **Register:** Visit the registration page to create a new user account.
- **Login:** Use the login page to access your account and perform CRUD operations on the To-do list App.
