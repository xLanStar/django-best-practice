:allow_comments: False

.. _environment-setup-environment:

====================
開發工具與執行環境
====================

.. _python-version-management:

-----------------
Python 執行環境
-----------------

建議使用 pyenv_ 來管理 Python 執行環境

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


.. _environment-dependency-management:

-----------------
Python 依賴管理
-----------------

建議使用 Poetry_ 來管理 Python 套件。

.. _Poetry: https://python-poetry.org/


安裝 Poetry_
================


.. tabs::
 .. tab:: Linux, macOS, Windows(WSL)

    .. code-block:: bash

        curl -sSL https://install.python-poetry.org | python3 -

 .. tab:: Windows (Powershell)

    .. code-block:: bash

        (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -


.. _install-dependencies:

新增依賴套件
=================

一律使用 Poetry_ 來安裝 Python 套件。

.. code-block:: bash

    poetry add package_name

.. note::

    你可以使用 ``poetry add --dev package_name`` 來安裝開發環境套件。


----------------
原始碼編輯器
----------------


目前只推薦使用 `Visual Studio Code`_ 作為原始碼編輯器。


.. _Visual Studio Code: https://code.visualstudio.com/

Python Langauge Server
========================

.. note::

    Language Server 是一個提供特定語言的程式碼智慧提示、自動完成、定義跳轉、語法檢查、型態檢查等功能的工具。
    使得開發者可以在編輯器中撰寫特定語言的程式碼。
    與 Linter 和 Formatter 不同，Linter 和 Formatter 主要用來檢查程式碼風格和格式化程式碼。


有許多 Python Language Server 可以使用，以下是一些常見的 Python Language Server:

- pyright_
- pylance_
- pylyzer_

.. _pyright: https://github.com/microsoft/pyright
.. _pylance: https://github.com/microsoft/pylance-release
.. _pylyzer: https://github.com/mtshiba/pylyzer

如果你是用 Visual Studio Code，建議安裝 `Pylance Extension <https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance>`_ 作為 Python Language Server。


--------------------------------
Python Linter 和 Formatter
--------------------------------

.. _environment-setup-environment-ruff:

Ruff
=================

Ruff_ 是一個 Python Linter 和 Formatter，用來檢查原始碼風格和格式化原始碼。
其取代了其他 Python Linter 和 Formatter，如 Flake8, Black, isort 等。因此不須再安裝這些套件。

.. _Ruff: https://github.com/astral-sh/ruff


安裝 Ruff_
----------------

.. code-block:: bash

    poetry add ruff


Lint
-----------------

使用以下指令來檢查原始碼風格:

.. code-block:: bash

    ruff check

設定原始法風格檢查規則，請參考 `Ruff Lint Settings <https://docs.astral.sh/ruff/settings/#lint>`_。


Format
-----------------

使用以下指令來格式化原始碼:

.. code-block:: bash

    ruff format

設定原始法格式化規則，請參考 `Ruff Format Settings <https://docs.astral.sh/ruff/settings/#format>`_。


.. _environment-setup-environment-ruff-settings:

設定
-----------------

Ruff 預設自動讀取 ``pyproject.toml`` 或 ``ruff.toml`` 或 ``.ruff.toml`` 設定檔。

以下是一個 ``pyproject.toml`` 範例設定檔:

.. code-block:: toml

    [tool.ruff]
    line-length = 120
    indent-width = 4
    target-version = "py313"

    [tool.ruff.lint]
    # Lint configuration

    [tool.ruff.format]
    # Format configuration

參考 `Ruff 官方文件 <https://docs.astral.sh/ruff/settings/>`_ 來設定 Ruff。

整合進原始碼編輯器
---------------------------

安裝
^^^^^^^^^^^^^^^^^

在 Visual Studio Code 中，你可以安裝 `Ruff Extension`_ 擴充套件來支援 Python 開發。

若你是用其他編輯器，請參考 `Ruff Editor Setup <https://docs.astral.sh/ruff/editors/setup/>`_。

使用
^^^^^^^^^^^^^^^^^

在 Visual Studio Code 中， `Ruff Extension`_ 會自動作為 Linter 檢查你的 Python Code。你可以使用 ``Ruff: Format`` 命令列或使用 ``Format Document With...`` 並選擇 ``Ruff`` 來格式化原始碼。


.. _Ruff Extension: https://marketplace.visualstudio.com/items?itemName=astralsh.ruff


設定
^^^^^^^^^^^^^^^^^

在原始碼編輯器中，你可以自訂修改 :ref:`Ruff Settings <environment-setup-environment-ruff-settings>` 來符合你的需求。參考 `Ruff 官方文件 <https://docs.astral.sh/ruff/settings/>`_ 來設定 Ruff。

以 Visual Studio Code 為例，你可以在 ``settings.json`` 中加入以下設定:

.. code-block:: json

    {
        "ruff.configuration": "~/path/to/ruff.toml"
    }
