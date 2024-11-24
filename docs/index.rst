:allow_comments: False

Django 最佳實踐文件
==================================

   本文為具有我個人觀點的 Django 最佳實踐，並不一定適用於所有情況。

本文件將介紹如何以最佳實踐的方式來建立一個以下列為主要目標的 Django 專案。

- 兼容水平擴展
- 高效
- 高安全性
- 易於維護
- 易於開發

具體來說，我們將使用以下技術來達到這些目標。

- 使用 pyenv_ 管理 Python 版本
- 使用 Poetry_ 管理 Python 套件
- 使用 ruff_ 作為 Linter 和 Formatter
   - 遵循 `Google Docstrings 風格 <https://google.github.io/styleguide/pyguide.html#38-comments-and-docstrings>`_
- 使用 Session 管理使用者登入狀態
- 使用 django-allauth_ 管理使用者帳號
   - 可使用 Email 或 Username 來登入
   - 整合 Google、Apple、Facebook 等第三方登入
   - 追蹤使用者登入狀態、IP 位置、裝置及歷史
   - 自訂 RestAPI 以兼容 React Native
- 整合 django-storages_ 管理靜態和媒體檔案
   - 使用 Backend 儲存靜態檔案
- 整合 django-ninja_
   - 使用 Router 管理 API 路由。
   - 自動產生 OpenAPI 文件。
- 使用 Redis_ 作為快取資料庫
   - 使用 Redis 來儲存 Session
   - 使用底層為 C 語言的 hiredis-py_ 程式庫來進一步提升 Redis 效能
- 使用 Celery_ 處理非同步任務

.. _ruff: https://github.com/astral-sh/ruff
.. _pyenv: https://github.com/pyenv/pyenv
.. _Poetry: https://python-poetry.org/
.. _django-allauth: https://django-allauth.readthedocs.io/en/latest/
.. _django-storages: https://django-storages.readthedocs.io/en/latest/
.. _django-ninja: https://django-ninja.rest-framework.com/
.. _hiredis-py: https://github.com/redis/hiredis-py
.. _Redis: https://redis.io/
.. _Celery: https://docs.celeryproject.org/en/stable/


.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: 環境
   :name: section-environment

   environment/setup-environment
   environment/setup-project
   environment/project-structure

.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: Cache 快取
   :name: section-cache

   cache/setup

.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: Session
   :name: section-session

   session/setup

.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: Authentification
   :name: section-authentification

   authentification/setup

.. toctree::
   :hidden:
   :maxdepth: 1
   :caption: 框架
   :name: section-framework

   framework/rest
