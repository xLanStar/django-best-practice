:allow_comments: False

.. _setup-session:

================
設定 Session
================


.. _session-setup-preface:

----------------
前言
----------------

使用 Cache 作為 Session 後端


.. _session-setup-settings:

-----------------
設定 settings
-----------------

`設定參考 <https://docs.djangoproject.com/en/5.1/topics/http/sessions/#settings>`_

.. note::
    請確保已設定 Cache，參考 :ref:`cache-setup`

.. code-block:: python

    # settings.py

    MIDDLEWARE  = [
        ...,
        django.contrib.sessions.middleware.SessionMiddleware,
        ...
    ]

    SESSION_ENGINE = 'django.contrib.sessions.backends.cache'
