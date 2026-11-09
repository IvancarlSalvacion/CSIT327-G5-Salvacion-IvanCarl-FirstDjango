# CampusConnect (FirstDjango)

**Name:** Ivan Carl Salvacion
**Section:** G5
**Course:** CSIT327

CampusConnect is a Django web app with user sign-up, login, and an editable
profile page, styled with Bootstrap 5 loaded from the CDN.

## Features

- **Sign-up** with a success message (Django messages framework) shown as a Bootstrap alert
- **Login / Logout** with styled forms
- **Profile page** built with Django's class-based `UpdateView`
  - Requires login (`LoginRequiredMixin`)
  - Users can only view and edit their own profile
  - Role and username cannot be changed from the profile form
- **Shared `base.html`** with Bootstrap 5 CDN links and a responsive navbar;
  every page uses `{% extends "base.html" %}`
- **CSRF protection** on all forms

## Tech Stack

- Python 3.12+
- Django 6.1.2
- SQLite
- Bootstrap 5.3 and Bootstrap Icons (CDN)

## How to Run

1. Clone the repository:
   ```bash
   git clone <your-repository-url>
   cd CSIT327-G5-Salvacion-IvanCarl-FirstDjango
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv venv
   venv\Scripts\activate        # Windows
   source venv/bin/activate     # macOS / Linux
   ```

3. Install the dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Apply the migrations:
   ```bash
   python manage.py migrate
   ```

5. Start the server:
   ```bash
   python manage.py runserver
   ```

6. Open http://127.0.0.1:8000/ in your browser.

## Pages

| URL | Description |
|---|---|
| `/accounts/signup/` | Create a new account |
| `/accounts/login/` | Log in |
| `/accounts/profile/` | View and edit your own profile (login required) |
| `/accounts/logout/` | Log out (POST) |

## Project Structure

```
campusconnect/      project settings and root URLs
accounts/           custom user model, forms, views, URLs
dashboard/          home and admin panel pages
templates/
  base.html         shared layout (Bootstrap CDN + navbar)
  registration/     login, signup, profile and form partials
  dashboard/        dashboard pages
```

## Running Tests

```bash
python manage.py test accounts
```
