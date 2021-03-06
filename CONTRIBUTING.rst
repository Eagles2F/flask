==========================
How to contribute to Flask
==========================

Thanks for considering contributing to Flask.

Support questions
=================

Please, don't use the issue tracker for this. Check whether the ``#pocoo`` IRC
channel on Freenode can help with your issue. If your problem is not strictly
Werkzeug or Flask specific, ``#python`` is generally more active.
`StackOverflow <https://stackoverflow.com/>`_ is also worth considering.

Reporting issues
================

- Under which versions of Python does this happen? This is even more important
  if your issue is encoding related.

- Under which versions of Werkzeug does this happen? Check if this issue is
  fixed in the repository.

Submitting patches
==================

- Include tests if your patch is supposed to solve a bug, and explain
  clearly under which circumstances the bug happens. Make sure the test fails
  without your patch.

- Try to follow `PEP8 <http://legacy.python.org/dev/peps/pep-0008/>`_, but you
  may ignore the line-length-limit if following it would make the code uglier.


Running the testsuite
---------------------

You probably want to set up a `virtualenv
<http://virtualenv.readthedocs.org/en/latest/index.html>`_.

The minimal requirement for running the testsuite is ``py.test``.  You can
install it with::

    pip install pytest

Clone this repository::

    git clone https://github.com/mitsuhiko/flask.git

Install Flask as an editable package using the current source::

    pip install --editable .

Then you can run the testsuite with::

    py.test

With only py.test installed, a large part of the testsuite will get skipped
though.  Whether this is relevant depends on which part of Flask you're working
on.  Travis is set up to run the full testsuite when you submit your pull
request anyways.

If you really want to test everything, you will have to install ``tox`` instead
of ``pytest``. Currently we're depending on a development version of Tox
because the released version is missing features we absolutely need. You can
install it with::

    pip install hg+https://bitbucket.org/hpk42/tox

The ``tox`` command will then run all tests against multiple combinations
Python versions and dependency versions.
