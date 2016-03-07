# auth_of_restful_api
Demo for authentication of RESTful API on Django

## Install requirements

```shell
pip install -r requirements.txt
```

## Start to demo

```shell
cd demo
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

feel free to visit http://127.0.0.1:8000/swagger/.

## Token based authentication

### Take auth_token

Input your username and password on http://127.0.0.1:8000/djoser/login/,
and you will get `auth_token` in response.

### Fetch user information

```shell
curl -H "Authorization: Token <the auth token>" http://127.0.0.1:8000/djoser/me/
```

### Change password

```shell
curl -X POST -H "Authorization: Token <the auth token>" -H "Content-Type: application/json" -d '{"current_password":"xxx","new_password":"yyy"}' http://127.0.0.1:8000/djoser/password/ 
```
