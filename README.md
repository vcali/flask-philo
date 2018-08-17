# Flask-Philo

Small and very opinionated framework to build flask based microservices.

You can check the official documentation [here](http://flask-philo.readthedocs.io/en/latest/)


## What is this project?

Flask is an awesome web microframework that works great out of the box. Nevertheless,
additional configuration and integration with complementary libraries are required
in order to build complex applications. Here in [riffstation.com](https://play.riffstation.com) we have several
HTTP REST based microservices, anytime that we want to create a new microservice we need to bootstrap
very similar common code.

This framework collect all the logic related with HTTP, REST and data access in one common place.
Feel free to use it and extend it. We are willing to hear about your suggestions and improvements.



## Basic Features

* REST out of the box.

* Simple sqlalchemy orm customized for postgresql with multiple dabatases.

* Unit testing tools

* Simple Redis integration.

* Simple Elastic Search integration.

* Basic AWS integration.



## Installation

```
$ pip3 install Flask-Philo
```




## Creating a new project
Flask-Philo includes the `flask-philo-admin` command line tool.
To quickly generate a new Flask-Philo project, navigate to the directory in which you want to create
the project and run:

```
$ flask-philo-admin startproject <project_name>
```

This will create a folder called project_name which will contain the basic structure of a Flask-Philo application,
basic unit tests and configuration.



### Folder structure

The following folder structure is created for the new project:

* README.md
* documentation
* src
    * app
        * __init__.py
        * models
        * serializers
        * urls.py
        * views
    * config
        * development.py
        * test.py
    * console_commands
        * __init__.py
    * manage.py
    * tests
        * __init__.py
        * test_views.py
* tools
    * requirements
        * base.txt
        * dev.txt


## Running the server for your new project

To run the listening server for your new Flask-Philo project, navigate to the project's ``src/`` directory and issue the ``runserver`` command :

```
    $ cd <your-project-dir>/src
    $ python3 manage.py runserver
```

The response from this command will be something like this:

```
    * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: 147-416-135
```


## Accessing the new Flask-Philo app

If you haven't already done so, run the following terminal command to create your Flask-Philo application:

```
    $ python3 manage.py runserver
```


Now, with the application running and with a route defined, the following URL address will be accessible in the browser of your choice, and will return a JSON response:

http://localhost:8080/example

Note that the port number (in this case ``8080``) should match the port number displayed when you start the application:

```
    # Port 8080 in this case
    * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    ...
```

Your browser will display a JSON response, as defined in the **ExampleView** class :

```
    {"some_data": "yes"}
```


Alternatively, you can test this example URL route with a direct HTTP request using the CURL command-line tool:

```
  $ curl http://localhost:8080/example
  {"some_data": "yes"}
```


All incoming request to your Flask-Philo application and their corresponding HTTP status codes may be viewed in the same console session you used to start the application:

```
    * Running on http://0.0.0.0:8080/ (Press CTRL+C to quit)
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: 147-416-135
    127.0.0.1 - - [05/Dec/2017 00:06:01] "GET /example HTTP/1.1" 200 -
```



## Executing Unit Tests

Flask-Philo simplifies Unit Test coverage by providing a single console command for running and managing all test. All test code should be written in the dedicated directory location : ``src/app/tests``. Within this directory, all Python source files begining with ``test_`` will be executed as part of a suite of Unit Tests.

To run all Unit Tests for your new Flask-Philo app, use the following console command:

```
    $ python3 manage.py test
```


The return of the tests will be something like the print below:


```
    ===================================== test session starts ======================================
    platform darwin -- Python 3.5.1, pytest-3.3.0, py-1.5.2, pluggy-0.6.0
    rootdir: <where_your_project_is>/flask-philo-example/src, inifile:
    collected 1 item

    tests/test_views.py .                                                                    [100%]

    =================================== 1 passed in 0.02 seconds ===================================
```


In this example, the automatically-generated example Unit Test class **TestExampleEndpoints** is executed, as defined in ``src/tests/test_views.py``








## External Resources

* [Flask Website](http://flask.pocoo.org/)

* [Flask Book](http://flaskbook.com/)

* [SQL Alchemy](http://www.sqlalchemy.org/)

* [Python Redis](https://pypi.python.org/pypi/redis/2.10.3)

* [Python Elastic Search](https://www.elastic.co/guide/en/elasticsearch/client/python-api/current/index.html)

* [AWS Boto](https://pypi.python.org/pypi/boto3)
