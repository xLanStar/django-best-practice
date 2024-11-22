:allow_comments: False

.. _environment-setup:

================
建置專案
================

.. _python-version-management:

-----------------
Python 版本管理
-----------------

建議使用 pyenv_ 來管理 Python 版本。

.. _pyenv:

安裝 pyenv_
================

.. tabs::
 .. tab:: Linux, Unix

    ::

        curl https://pyenv.run | bash
 .. tab:: macOS

    ::

        brew update
        brew install pyenv

 .. tab:: Windows (WSL)

    .. warning::

        目前 pyenv 不支援 Windows，請使用 pyenv-win_。

    ::

        Invoke-WebRequest -UseBasicParsing -Uri "https://raw.githubusercontent.com/pyenv-win/pyenv-win/master/pyenv-win/install-pyenv-win.ps1" -OutFile "./install-pyenv-win.ps1"; &"./install-pyenv-win.ps1"


.. _pyenv-win: https://github.com/pyenv/pyenv


.. _python-dependency-management:

-----------------
Python 套件管理器
-----------------

建議使用 Poetry_ 來管理 Python 套件。

.. _Poetry: https://python-poetry.org/


安裝 Poetry_
================


.. tabs::
 .. tab:: Linux, macOS, Windows(WSL)

    ::

        curl -sSL https://install.python-poetry.org | python3 -

 .. tab:: Windows (Powershell)

    ::

        (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -

.. _install-dependencies:

新增依賴套件
=================

一律使用 Poetry_ 來安裝 Python 套件。

::

    poetry add package_name

.. note::

    你可以使用 ``poetry add --dev package_name`` 來安裝開發環境套件。


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
