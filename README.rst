===========
rabinmiller
===========

Pure-Python implementation of the `Rabin-Miller primality test <https://en.wikipedia.org/wiki/Rabin-Miller_primality_test>`__.

|pypi| |readthedocs| |actions| |coveralls|

.. |pypi| image:: https://badge.fury.io/py/rabinmiller.svg#
   :target: https://badge.fury.io/py/rabinmiller
   :alt: PyPI version and link.

.. |readthedocs| image:: https://readthedocs.org/projects/rabinmiller/badge/?version=latest
   :target: https://rabinmiller.readthedocs.io/en/latest/?badge=latest
   :alt: Read the Docs documentation status.

.. |actions| image:: https://github.com/lapets/rabinmiller/workflows/lint-test-cover-docs/badge.svg#
   :target: https://github.com/lapets/rabinmiller/actions/workflows/lint-test-cover-docs.yml
   :alt: GitHub Actions status.

.. |coveralls| image:: https://coveralls.io/repos/github/lapets/rabinmiller/badge.svg?branch=main
   :target: https://coveralls.io/github/lapets/rabinmiller?branch=main
   :alt: Coveralls test coverage summary.

Purpose
-------
This library provides a pure-Python implementation of the `Rabin-Miller primality test <https://en.wikipedia.org/wiki/Rabin-Miller_primality_test>`__. Based on a `simple implementation <https://rosettacode.org/wiki/Miller%E2%80%93Rabin_primality_test#Python>`__, this library prioritizes portability and readability. If performance is a priority, `other libraries <https://pypi.org/project/miller-rabin/>`__ may be more appropriate.

Installation and Usage
----------------------
This library is available as a `package on PyPI <https://pypi.org/project/rabinmiller>`__:

.. code-block:: bash

    python -m pip install rabinmiller

The library can be imported in the usual way:

.. code-block:: python

    from rabinmiller import rabinmiller

Development
-----------
All installation and development dependencies are fully specified in ``pyproject.toml``. The ``project.optional-dependencies`` object is used to `specify optional requirements <https://peps.python.org/pep-0621>`__ for various development tasks. This makes it possible to specify additional options (such as ``docs``, ``lint``, and so on) when performing installation using `pip <https://pypi.org/project/pip>`__:

.. code-block:: bash

    python -m pip install ".[docs,lint]"

Documentation
^^^^^^^^^^^^^
The documentation can be generated automatically from the source files using `Sphinx <https://www.sphinx-doc.org>`__:

.. code-block:: bash

    python -m pip install ".[docs]"
    cd docs
    sphinx-apidoc -f -E --templatedir=_templates -o _source .. && make html

Testing and Conventions
^^^^^^^^^^^^^^^^^^^^^^^
All unit tests are executed and their coverage is measured when using `pytest <https://docs.pytest.org>`__ (see the ``pyproject.toml`` file for configuration details):

.. code-block:: bash

    python -m pip install ".[test]"
    python -m pytest

Alternatively, all unit tests are included in the module itself and can be executed using `doctest <https://docs.python.org/3/library/doctest.html>`__:

.. code-block:: bash

    python src/rabinmiller/rabinmiller.py -v

Style conventions are enforced using `Pylint <https://pylint.readthedocs.io>`__:

.. code-block:: bash

    python -m pip install ".[lint]"
    python -m pylint src/rabinmiller

Contributions
^^^^^^^^^^^^^
In order to contribute to the source code, open an issue or submit a pull request on the `GitHub page <https://github.com/lapets/rabinmiller>`__ for this library.

Versioning
^^^^^^^^^^
The version number format for this library and the changes to the library associated with version number increments conform with `Semantic Versioning 2.0.0 <https://semver.org/#semantic-versioning-200>`__.

Publishing
^^^^^^^^^^
This library can be published as a `package on PyPI <https://pypi.org/project/rabinmiller>`__ via the GitHub Actions workflow found in ``.github/workflows/build-publish-sign-release.yml`` that follows the `recommendations found in the Python Packaging User Guide <https://packaging.python.org/en/latest/guides/publishing-package-distribution-releases-using-github-actions-ci-cd-workflows/>`__.

Ensure that the correct version number appears in ``pyproject.toml``, and that any links in this README document to the Read the Docs documentation of this package (or its dependencies) have appropriate version numbers. Also ensure that the Read the Docs project for this library has an `automation rule <https://docs.readthedocs.io/en/stable/automation-rules.html>`__ that activates and sets as the default all tagged versions.

To publish the package, create and push a tag for the version being published (replacing ``?.?.?`` with the version number):

.. code-block:: bash

    git tag ?.?.?
    git push origin ?.?.?
