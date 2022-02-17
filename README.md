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