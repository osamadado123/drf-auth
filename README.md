# Project: Permissions & Postgresql

## Author: Osama Maher

## Setup

- activate virtual enviroment with `source .venv/bin/activate`
- then run `docker-compose up --build`
- open a split terminal and run this command `docker-compose run web python manage.py migrate`
- create super user with this command `docker-compose run web python manage.py createsuperuser`

## post man tests

my super user is (username) osama (password) osama

- using this path `localhost:8000/api/v1/snacks/` with basic auth by adding username and password you can post a new snack
- using this path `localhost:8000/api/token/` with bearer token adding `{"username": "osama ","password":"osama"}` to the body as json file
and send a post requiest you will get refresh and access token like this

```
{
    "refresh": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImV4cCI6MTY3MTU2MDgxMywiaWF0IjoxNjcxNDc0NDEzLCJqdGkiOiJjNjYzZGNhOTdjNTQ0YTlkYTFiNjdhODUxM2FiNGNlMiIsInVzZXJfaWQiOjEsInVzZXJuYW1lIjoib3NhbWEifQ.R8vnP__MmWY1420AhYY_IHB9WO3f9WAGXA2P88tw48c",
    "access": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNjcxNDc0NzEzLCJpYXQiOjE2NzE0NzQ0MTMsImp0aSI6ImVlODU1NmYwOTliNDQ0NWFiYzA3ZWUyZjczY2NjZjRkIiwidXNlcl9pZCI6MSwidXNlcm5hbWUiOiJvc2FtYSJ9.H1D1WxFk2PW8ZgAgRKg-pECnDdU2RbzDhTLrT14Cvng"
}
```
- using this path `http://localhost:8000/api/token/refresh/` and add the refresh token from earlier and send a post request 
you will get a new access token

## pull request 
[my pull request]()
