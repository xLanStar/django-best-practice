:allow_comments: False

.. _cache-setup:

================
設定快取
================

.. _cache-setup-preface:

---------------------
前言
---------------------

使用 Redis 作為快取資料庫


.. _cache-setup-settings:

---------------------
設定 settings
---------------------

`設定參考 <https://docs.djangoproject.com/en/5.1/topics/cache/#redis>`_

.. code-block:: python

    # settings.py

    CACHES = {
        'default': {
            'BACKEND': 'django_redis.cache.RedisCache',
            'LOCATION': 'redis://127.0.0.1:6379/0',
            'OPTIONS': {
                'CLIENT_CLASS': 'django_redis.client.DefaultClient',
                'PARSER_CLASS': 'redis.connection.HiredisParser',
            }
        }
    }

---------------------
安裝 redis-py_
---------------------

::

    poetry add redis

.. note::
    建議額外安裝 hiredis-py_ 以提升 Redis 效能::

        poetry add hiredis

    安裝之後，redis-py_ 會自動使用 hiredis-py_ 來提升效能。


.. _redis-py: https://github.com/redis/redis-py
.. _hiredis-py: https://github.com/redis/hiredis-py
