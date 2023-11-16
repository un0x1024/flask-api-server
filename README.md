## [Flask API Server](https://github.com/un0x1024/flask-api-server)

![Flask API Server - Open-source Flask Starter provided by AppSeed.](https://user-images.githubusercontent.com/51070104/126349643-264d4cf4-6d0b-4c24-8185-adf69409fa4e.png)

<br />

## ✨ Quick Start in `Docker`

> Get the code

```bash
$ git clone https://github.com/un0x1024/flask-api-server.git
$ cd flask-api-server
```

> Start the app in Docker

```bash
$ docker-compose up --build  
```

The API server will start using the PORT `5000`.

<br />

<br />

## ✨ How to use the code

> **Step #1** - Clone the project

```bash
$ git clone https://github.com/un0x1024/flask-api-server.git
$ cd flask-api-server
```

<br />

> **Step #2** - create virtual environment using python3 and activate it (keep it outside our project directory)

```bash
$ # Virtualenv modules installation (Unix based systems)
$ virtualenv env
$ source env/bin/activate
$
$ # Virtualenv modules installation (Windows based systems)
$ # virtualenv env
$ # .\env\Scripts\activate
```

<br />

> **Step #3** - Install dependencies in virtualenv

```bash
$ pip install -r requirements.txt
```

<br />

> **Step #4** - setup `flask` command for our app

```bash
$ export FLASK_APP=run.py
$ export FLASK_ENV=development
```

 For **Windows-based** systems

```powershell
$ (Windows CMD) set FLASK_APP=run.py
$ (Windows CMD) set FLASK_ENV=development
$
$ (Powershell) $env:FLASK_APP = ".\run.py"
$ (Powershell) $env:FLASK_ENV = "development"
```

<br />

> **Step #5** - Create a new `.env` file using sample `env.sample`

The meaning of each variable can be found below:

- `DEBUG`: if `True` the app runs in develoment mode
  - For production value `False` should be used
- `SECRET_KEY`: used in assets management
- `GITHUB_CLIENT_ID`: For GitHub social login
- `GITHUB_SECRET_KEY`: For GitHub social login

<br />

> **Step #6** - start test APIs server at `localhost:5000`

```bash
$ flask run
```

Use the API via `POSTMAN` or Swagger Dashboard.

![Flask API Server - Swagger Dashboard.](https://user-images.githubusercontent.com/51070104/141950891-ea315fca-24c2-4929-841c-38fb950a478d.png)

<br />

## ✨ Project Structure

```bash
flask-api-server/
├── api
│   ├── config.py
│   ├── __init__.py
│   ├── models.py
│   └── routes.py
├── Dockerfile
├── README.md
├── requirements.txt
├── run.py
└── tests.py
```

<br />

## ✨ API

For a fast set up, use this `POSTMAN` file: [api_sample](https://github.com/app-generator/api-unified-definition/blob/main/api.postman_collection.json)

> **Register** - `api/users/register` (**POST** request)

```
POST api/users/register
Content-Type: application/json

{
    "username":"test",
    "password":"pass", 
    "email":"test@appseed.us"
}
```

<br />

> **Login** - `api/users/login` (**POST** request)

```
POST /api/users/login
Content-Type: application/json

{
    "password":"pass", 
    "email":"test@appseed.us"
}
```

<br />

> **Logout** - `api/users/logout` (**POST** request)

```
POST api/users/logout
Content-Type: application/json
authorization: JWT_TOKEN (returned by Login request)

{
    "token":"JWT_TOKEN"
}
```

<br />

## ✨ Testing

Run tests using `pytest tests.py`

<br />

thank for ` https://github.com/app-generator/api-server-flask`
