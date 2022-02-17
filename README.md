# Bookstore Project

### Run app with docker-compose.yml
```docker-compose down```
```docker-compose up -d --build```
```docker-compose exec web python manage.py makemigrations ```
```docker-compose exec web python manage.py migrate```

### Create superuser
```docker-compose exec web python manage.py createsuperuser```

### Run tests
```docker-compose exec web python manage.py test```

### Check for deploy
```docker-compose exec web python manage.py check --deploy```


### Run app with docker-compose-prod.yml
```docker-compose down```
```docker-compose -f docker-compose-prod.yml up -d --build```
```docker-compose exec web python manage.py makemigrations ```
```docker-compose exec web python manage.py migrate```


### Generate secret key
```docker-compose exec web python -c 'import secrets; print(secrets.token_urlsafe(38))'```

### Collect static
```docker-compose exec web python manage.py collectstatic```


### For deploy at heroku
login to heroku: ```heroku login```
create heroku.yml: ```touch heroku.yml```
create heroku app: ```heroku create```
setup container: ```heroku stack:set container -a app_name_here```
setup db: ```heroku addons:create heroku-postgresql:hobby-dev -a app_name_here```
set git remote heroku: ```heroku git:remote -a app_name_here```
push code to heroku: ```git push heroku main``` or ```git push heroku master```
to migrate db: ```heroku run python manage.py migrate```
to create superuser: ```heroku run python manage.py createsuperuser```

TO OPEN APP: ```heroku open -a app_name_here```