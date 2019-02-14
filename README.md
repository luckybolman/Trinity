<p align="center">
  <img src="https://i.imgur.com/RLmwuQK.png" alt="Trinity-py"/>
</p>

[![stability-experimental](https://img.shields.io/badge/stability-stable-green.svg)](https://github.com/emersion/stability-badges#stable)
[![PEP8](https://img.shields.io/badge/code%20style-pep8-orange.svg)](https://www.python.org/dev/peps/pep-0008/)

###### Using least ammount of modules possible
flask, flask-compress, pymysql, passlib, ujson, argon2_cffi (encryption backend)

How to setup
-------------------
- Install Python 3.6+
https://www.python.org/

- Install MySQL Server
https://www.apachefriends.org/index.html

- Configure `config.json`
- Import `mysqldb.sql` into your database. (default user included tr4-admin:password)

--------------------
Run the command below to install required modules. (pip or pip3)

```sh
$ pip install -r requirements.txt
```

How to run
----------------
<b>Trinity was built with compatibility in mind for multiple setups.</b> 

#### Local / development environment
```sh
$ python local_server.py
```
###### Windows users can simply launch `win_launch.bat`
--------------------

#### Gunicorn production environment
###### *Recommended way* (docs: <a href="http://docs.gunicorn.org/en/stable/run.html">gunicorn docs</a> <a href="https://djangodeployment.com/2016/11/30/how-to-setup-apache-with-gunicorn/">apache/nginx+gunicorn docs</a>)
```sh
$ gunicorn --workers=4 app:app
```
#### Passenger production environment
- See `passenger_wsgi.py`
###### (http://griimnak.me/trinity runs on passenger through cpanel)

#### Windows waitress production environment
###### *Waitress is a gunicorn alternative for windows.* 
```sh
$ pip install waitress
$ waitress-serve --listen=127.0.0.1:80 -w 4 app:app
```
----------------
