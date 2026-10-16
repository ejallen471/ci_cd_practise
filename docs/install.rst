Installation
============

This is my documentation change :)

You will need Python 3.12 or later and a local copy of this repository.
Open a terminal in the repository directory, where ``pyproject.toml`` is located.

Create a virtual environment
----------------------------

On macOS or Linux:

.. code-block:: bash

   python3 -m venv .venv
   source .venv/bin/activate

On Windows, using PowerShell:

.. code-block:: powershell

   python -m venv .venv
   .\.venv\Scripts\Activate.ps1

On Windows, using Command Prompt, activate the environment with
``.venv\Scripts\activate.bat`` instead.

Install the package
-------------------

With the environment activated, install the package and the development and
documentation tools:

.. code-block:: bash

   python -m pip install -e ".[dev,docs]"

The ``-e`` option installs the package in editable mode, so changes to its Python
source are available without reinstalling. The extras install tools including
pytest, Ruff, and Sphinx; NumPy is installed as a package dependency.

Check that the command is available by summarising the bundled sample data:

.. code-block:: bash

   ci-course

Continue to :doc:`quickstart` for a worked example.
