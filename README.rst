==================
QI Python template
==================

Python package template for bioinformatics software. Based on Cookiecutter_. Forked from https://github.com/audreyr/cookiecutter-pypackage/

* GitHub repo: https://github.com/happykhan/qi-python-package
* Cookiecutter Documentation: https://cookiecutter-pypackage.readthedocs.io/
* Free software: BSD license

Features
--------

* Testing setup with ``unittest`` and ``python setup.py test`` or ``py.test``
* Travis-CI_: Ready for Travis Continuous Integration testing
* Tox_ testing: Setup to easily test for Python 2.7, 3.4, 3.5, 3.6
* Sphinx_ docs: Documentation ready for generation with, for example, ReadTheDocs_
* Dockerfile included.
* Auto-release to PyPI_ when you push a new tag to master (optional)
* Command line interface using Click (optional)

.. _Cookiecutter: https://github.com/audreyr/cookiecutter


Build Status
-------------

Linux:

.. image:: https://img.shields.io/travis/audreyr/cookiecutter-pypackage.svg
    :target: https://travis-ci.org/audreyr/cookiecutter-pypackage
    :alt: Linux build status on Travis CI

Windows:

.. image:: https://ci.appveyor.com/api/projects/status/github/happykhan/qi-python-package?branch=master&svg=true
    :target: https://ci.appveyor.com/project/happykhan/qi-python-package/branch/master
    :alt: Windows build status on Appveyor

Security & Dependencies:

.. image:: https://pyup.io/repos/github/happykhan/qi-python-package/shield.svg
     :target: https://pyup.io/repos/github/happykhan/qi-python-package/
     :alt: Updates

Quickstart
----------

Install the latest Cookiecutter if you haven't installed it yet (this requires
Cookiecutter 1.4.0 or higher)::

    pip install -U cookiecutter

Generate a Python package project::

    cookiecutter https://github.com/happykhan/qi-python-package

Then:

* Create a repo and put it there.
* Add the repo to your Travis-CI_ account.
* Install the dev requirements into a virtualenv. (``pip install -r requirements_dev.txt``)
* Register_ your project with PyPI.
* Run the Travis CLI command `travis encrypt --add deploy.password` to encrypt your PyPI password in Travis config
  and activate automated deployment on PyPI when you push a new tag to master branch.
* Add the repo to your ReadTheDocs_ account + turn on the ReadTheDocs service hook.
* Release your package by pushing a new tag to master.
* Add a `requirements.txt` file that specifies the packages you will need for
  your project and their versions. For more info see the `pip docs for requirements files`_.
* Activate your project on `pyup.io`_.
* Activate your project on `Docker`_.
* **If you can change the default values for projects in cookiecutter.json**

.. _`pip docs for requirements files`: https://pip.pypa.io/en/stable/user_guide/#requirements-files
.. _Register: https://packaging.python.org/distributing/#register-your-project

Worked Example
--------------
For more details, see the `cookiecutter-pypackage tutorial`_. 

Getting started

.. code-block:: bash

    cd ~/code # Some directory where you want your code
    pip install -U cookiecutter
    cookiecutter https://github.com/happykhan/qi-python-package    
    # Follow the cookiecutter interactive prompts; I created a project called 'the best program'
    # Add a repo for github at https://github.com/new 
    cd the_best_program # folder with the new template code
    git init
    git add .
    git commit -m 'The beginning of something great'
    git remote add origin git@github.com:happykhan/the-best-program.git
    git push -u origin master
    # Go to https://travis-ci.org/account/repositories & add the repo. e.g. 'the-best-program'
    # Create a virtualenv 
    virtualenv -p /usr/bin/python3 .venv
    source .venv/bin/activate
    pip install -r requirements_dev.txt
    # Add the repo in https://readthedocs.org/dashboard/import/
    # Add the repo in https://pyup.io/account/repos/add/ 
    # Add the repo in https://hub.docker.com
    # If you're developing for Windows, add your repo to appveyor https://ci.appveyor.com/projects
    

Now start writing code, be sure to commit changes to GitHub regularly, write tests (run with `python setup.py  test`), and document your program. When you want to package your project on pypi, try the following:

.. code-block:: bash

    # Create wheels/binaries for pypi
    python3 setup.py sdist bdist_wheel
    # Upload to pypi using twine.
    twine upload  dist/*
    
Everyone can now install your program in one line, using pip `pip install the-best-program`.    
You can also get your program into Docker:

.. code-block:: bash

    docker  build -t thebestprogram .
    docker login
    docker tag thebestprogram happykhan/thebestprogram:0.1.0
    docker push happykhan/best:0.1.0

You can also set up automatic hooks, that build a new container on every GitHub commit see hub.docker.com
For more details, see the `cookiecutter-pypackage tutorial`_.


.. _`cookiecutter-pypackage tutorial`: https://cookiecutter-pypackage.readthedocs.io/en/latest/tutorial.html


.. _Travis-CI: http://travis-ci.org/
.. _Tox: http://testrun.org/tox/
.. _Sphinx: http://sphinx-doc.org/
.. _ReadTheDocs: https://readthedocs.io/
.. _`pyup.io`: https://pyup.io/
.. _Bumpversion: https://github.com/peritus/bumpversion
.. _Punch: https://github.com/lgiordani/punch
.. _PyPi: https://pypi.python.org/pypi
.. _Docker: https://hub.docker.com
