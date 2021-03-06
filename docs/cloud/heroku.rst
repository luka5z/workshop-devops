Heroku
======

Tworzenie aplikacji w oparciu o platformę Heroku
------------------------------------------------

-  Tworzenie aplikacji
-  Storage
-  Cache
-  Bazy danych


Set up
^^^^^^

.. code:: sh

    heroku login

Prepare the app
^^^^^^^^^^^^^^^

.. code:: sh

    git clone https://github.com/heroku/python-getting-started.git
    cd python-getting-started

Deploy the app
^^^^^^^^^^^^^^

.. code:: sh

    heroku create
    git push heroku master
    heroku ps:scale web=1

View logs
^^^^^^^^^

.. code:: sh

    heroku logs --tail

Define a Procfile
^^^^^^^^^^^^^^^^^

.. code:: text

    web: gunicorn gettingstarted.wsgi --log-file -
    web: python manage.py runserver 0.0.0.0:5000

Scale the app
^^^^^^^^^^^^^

.. code:: sh

    heroku ps
    heroku ps:scale web=0
    heroku ps:scale web=1

Declare app dependencies
^^^^^^^^^^^^^^^^^^^^^^^^

-  ``requirements.txt``

Run the app locally
^^^^^^^^^^^^^^^^^^^

.. code:: sh

    heroku local web -f Procfile.windows
    heroku local web

Push local changes
^^^^^^^^^^^^^^^^^^

.. code:: sh

    git commit -am "Changes"
    git push heroku master

Provision add-ons
^^^^^^^^^^^^^^^^^

.. code:: sh

    heroku addons:create papertrail
    heroku addons
    heroku addons:open papertrail

Start a console
^^^^^^^^^^^^^^^

.. code:: sh

    heroku run python manage.py shell
    heroku run bash

Define config vars
^^^^^^^^^^^^^^^^^^

.. code:: sh

    heroku config:set TIMES=2
    heroku config

Provision a database
^^^^^^^^^^^^^^^^^^^^

.. code:: sh

    heroku addons
    heroku config
    heroku pg
    heroku pg:psql


Zadania
-------

Uruchamianie aplikacji
^^^^^^^^^^^^^^^^^^^^^^
- Ściągnij repozytorium:
    - https://github.com/AstroMatt/esa-time-perception

- Załóż konto na `Heroku`
- Stwórz nową aplikację
- Dodaj remote `Heroku` do lokalnego repozytorium `GIT`
- Uruchom aplikację na `Heroku`
- Uruchom polecenie na platformie w cloud:

.. code-block:: sh

    python manage.py migrate

- Zrób dump bazy danych
