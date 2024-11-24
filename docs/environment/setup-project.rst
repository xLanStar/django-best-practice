:allow_comments: False

.. _environment-setup-project:

================
建置專案
================

    若你還沒建置好開發環境，請參考 :ref:`environment-setup-environment` 來建置開發環境。


.. _create-new-project:

-----------------
創建新專案
-----------------


.. _create-new-project-initialize:


初始化專案
=================

::

    poetry new project_name


.. _create-new-project-virutal:

創建虛擬環境
=================

之後，可以在專案目錄使用以下命令來創建虛擬環境::

    poetry env use 3.13

.. note:: 你可以替換 ``3.13`` 為你想要的 Python 版本。


.. _activate-virtual-environment:

啟用虛擬環境
=================

::

    poetry shell


.. _django-management:

----------------
建置 Django 專案
----------------

.. _install-django:

安裝 Django
=================

::

    poetry add django


.. _create-django-project:

創建 Django 專案
=================

::

    python django-admin startproject config .


.. _add-django-app:

新增 Django 應用
=================

::

    python manage.py startapp app_name


.. _run-django-project:

執行 Django 專案
=================

::

    python manage.py runserver

.. _run-django-migrations:

執行 Django 遷移
=================


若有新的模型，或模型有更動，請執行以下命令來創建遷移檔案::

    python manage.py makemigrations


接著，執行遷移檔案來更新資料庫::

    python manage.py migrate


.. _run-django-tests:

執行 Django 測試
=================

::

    python manage.py test
