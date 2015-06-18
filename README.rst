django-migration-compass
====================


What is it?
-----------

Django migration compass is a tool to guide your django migrations through git branch switches.

It is a git hook that keeps your django migrations in sync with your repository as you move around.

Note: the packages and executable are still named django-south because I haven't changed them yet, but there are no dependencies on South. This is meant for Django 1.7+

Installation
------------

.. code-block:: bash

    $ pip install django-south-compass

Usage
-----

Go to your git repo and do:

.. code-block:: bash

    $ django-south-compass install

This will set up a git hook so that whenever you checkout a branch, your
migrations are synced up.

E.g.

.. code-block:: bash

    $ git branch
        * master
        feature1
        feature2

    $ git checkout feature1
    # Migrates to any new migrations added in feature1

    $ git checkout master
    # Migrates back to the last migration in master

    $ git checkout feature2
    # Migrates to any new migrations added in feature2

    $ git checkout feature1
    # Migrates back to the last migration common between
    # feature1 and feature2, then migrates forward to feature1


License
-------

3 Clause BSD.


Thanks
------

Django migration compass was almost entirely written by agiliq. I just tweaked it for modern Django. 
