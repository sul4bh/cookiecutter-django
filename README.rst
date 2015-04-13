cookiecutter-django
=======================

A cookiecutter_ template for Django. Based on cookiecutter-django_

.. _cookiecutter: https://github.com/audreyr/cookiecutter
.. _cookiecutter-django: https://github.com/pydanny/cookiecutter-django

Please update your version of cookiecutter!
--------------------------------------------

This cookiecutter template uses features that exists only in cookiecutter 0.9.0 or higher.

Features
---------

* For Django 1.8
* Twitter Bootstrap_ 3
* Settings management via django-configurations_

.. _Bootstrap: https://github.com/dyve/django-bootstrap3
.. _django-configurations: https://github.com/jezdez/django-configurations

Constraints
-----------

* Environment variables for configuration (This won't work with Apache/mod_wsgi).


Usage
------

Let's pretend you want to create a Django project called "redditclone". Rather than using `startproject`
and then editing the results to include your name, email, and various configuration issues that always get forgotten until the worst possible moment, get cookiecutter_ to do all the work.

First, get cookiecutter. Trust me, it's awesome::

    $ pip install cookiecutter

Now run it against this repo::

    $ cookiecutter https://github.com/sul4bh/cookiecutter-django.git

You'll be prompted for some questions, answer them, then it will create a Django project for you.

Enter the project and take a look around::

    $ cd redditclone/
    $ ls


Getting up and running
----------------------

The steps below will get you up and running with a local development environment. We assume you have the following installed:

* pip
* virtualenv
* PostgreSQL

First make sure to create and activate a virtualenv_, then open a terminal at the project root and install the requirements for local development::

    $ pip install -r requirements/local.txt

.. _virtualenv: http://docs.python-guide.org/en/latest/dev/virtualenvs/

Create a copy of config/local.py.dist file and name it config/local.py. Do not add this file to version control as it contains developer specific settings. (ignored in .gitignore)
Then, create a MySQL database and add the database configuration using the  ``dj-database-url`` app pattern: ``postgres://db_owner:password@dbserver_ip:port/db_name`` either:

* in the ``config.local.py`` setting file,
* or in the env variable ``DATABASE_URL``


You can now run the usual Django ``migrate`` and ``runserver`` command (replace ``yourapp`` with the name of the directory containing the Django project)::

    $ python yourapp/manage.py migrate

    $ python yourapp/manage.py runserver


"Your Stuff"
-------------

Scattered throughout the Python and HTML of this project are places marked with "your stuff". This is where third-party libraries are to be integrated with your project.
