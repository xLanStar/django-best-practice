:allow_comments: False

.. _project-structure:

================
專案架構
================


.. _folder-strucutre:

----------------
目錄結構
----------------

Django 專案的目錄結構應該如下::

    project_name/
    ├── app1/
    │   ├── migrations/
    │   ├── templates/
    │   ├── tests/
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py
    │   ├── models.py
    │   └── api.py
    │── app2/
    │   ├── migrations/
    │   ├── templates/
    │   ├── tests/
    │   ├── __init__.py
    │   ├── admin.py
    │   ├── apps.py
    │   ├── models.py
    │   └── api.py
    ├── config/
    │   ├── settings/
    │   │   ├── __init__.py
    │   │   ├── base.py
    │   │   ├── local.py
    │   │   └── production.py
    │   ├── __init__.py
    │   ├── asgi.py
    │   ├── api.py
    │   ├── urls.py
    │   └── wsgi.py
    ├── locale/
    │   ├── zh_Hant/
    │   │   └── LC_MESSAGES/
    │   │       ├── django.mo
    │   │       └── django.po
    ├── static/
    ├── templates/
    ├── tests/
    ├── utils/
    ├── .gitignore
    ├── .env
    ├── .env.example
    ├── media/
    ├── manage.py
    ├── poetry.lock
    ├── pyproject.toml
    └── README.md
