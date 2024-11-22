:allow_comments: False

.. _rest-setup:

================
Rest 框架
================

.. _rest-setup-preface:

----------------
前言
----------------

使用 django-ninja_ 作為 Restful API 框架


.. _rest-setup-settings:

----------------
設定 settings
----------------

`設定參考 <https://django-ninja.dev/reference/settings/>`_

.. code-block:: python

    # settings.py
    NINJA_PAGINATION_CLASS = "ninja.pagination.LimitOffsetPagination"

    NINJA_PAGINATION_PER_PAGE = 100


.. _django-ninja: https://django-ninja.rest-framework.com/
