# UselessDjangoApp
This is a useless webapp (just for practice)

# Deploying Process
## Video Tutorial
[Click here to see the video](https://youtu.be/fH2S5lWNKaM "heroku deployment for django-sqlite3 app")

## Textual
1. At first [create account](https://www.heroku.com "heroku.com") or [login](https://id.heroku.com/login "heroku login") in heroku
1. Download `heroku-cli` from [here](https://cli-assets.heroku.com/heroku-x64.exe "click here") or [visit the website](https://devcenter.heroku.com/articles/heroku-cli#download-and-install "click here")

- **Create a virtual environment:**
```terminal
pip install virtualenv
```
```terminal
virtualenv anyname
```
- After creating virtual environment activate your vitualenv
```terminal
pip install django gunicorn django-heroku
```

`You can run specific version like pip install django==2.2`

- Move your django-project in that virtual environment
- Add your dependencies to requirements.txt by typing in the terminal
```bash
pip freeze > requirements.txt
```

### Setup your django-project before starting `heroku-deployment`
- Don't forget to add this in **settings.py**
```python
STATICFILES_DIRS = [
    os.path.join(BASE_DIR, "static")
]
```
- First, and most importantly, Heroku web applications require a `Procfile`

This file is used to explicitly declare your application’s process types and entry points. It is located in the root of your repository

#### Procfile
```Procfile
web: gunicorn yourprojectname.wsgi --log-file -
```