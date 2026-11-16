# moviereviews

A Django web application where visitors can browse a catalog of movies and registered users can write reviews for them. The project was generated with Django 2.2 and uses SQLite for storage.

## Features

- Movie list on the home page with search by title (`searchMovie` query parameter).
- Movie detail page showing the movie and its reviews.
- User sign up, login and logout (Django's built-in auth).
- Logged-in users can create reviews (text and a "watch again" flag), and edit or delete their own reviews.
- A `News` model (headline, body, date) with a `news/` route.
- Movies and news are managed through the Django admin; movie posters are uploaded to `media/movie/images/`.

## Tech stack

- Python 3, Django 2.2 (per the generated settings)
- SQLite
- Pillow (required by Django's `ImageField`)
- Django templates (HTML)

## Project structure

```
manage.py
moviereviews/   project settings, root URLs, base template, static files
movie/          Movie and Review models, views, forms, templates
accounts/       sign up / login / logout views and templates
news/           News model and views
media/          uploaded movie images
```

## Getting started

The repository has no requirements file, so install the dependencies manually:

```bash
python -m venv venv
source venv/bin/activate
pip install "django>=2.2,<3" pillow
python manage.py migrate
python manage.py createsuperuser   # to add movies via /admin/
python manage.py runserver
```

Then open http://127.0.0.1:8000/. The SQLite database (`db.sqlite3`) is not included in the repository and is created by `migrate`.

## License

See the [LICENSE](LICENSE) file.
