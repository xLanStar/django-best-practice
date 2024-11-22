:allow_comments: False

.. _authentification-setup:

=======================
設定 Authentification
=======================

.. _authentification-setup-preface:

使用 django-allauth 作為使用者帳號管理套件


.. _authentification-setup-settings:

---------------------
設定 settings
---------------------



.. code-block:: python

    INSTALLED_APPS = [
        ...,
        'allauth',
        'allauth.account',
        'allauth.socialaccount',
        'allauth.socialaccount.providers.google',
        'allauth.socialaccount.providers.apple',
        'allauth.socialaccount.providers.facebook',
        ...
    ]

.. _authentification-setup-settings-account:


帳號相關設定
=============

`設定參考 <https://docs.allauth.org/en/latest/account/configuration.html>`_



-------------
其他注意事項
-------------

.. warning::

    ALLOW_HOSTS 必須設定為正確的前端網域，否則會導致請求第三方登入重導向時發生錯誤。

.. warning::

    系統時間不可過慢，否則會導致 Google 身分驗證失敗。
