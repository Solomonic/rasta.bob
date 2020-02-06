rasta.bob
======

``rasta.bob`` provides useful `mr.bob`_ templates to generate products for a JAM Stack Ecommerce.

To create a new product::

    $ mrbob rasta.bob:product


Available Templates
===================

- product


Options
=======

On creating a package you can choose from the following options. The default value is in [square brackets].


Plone and Diazo Packages
------------------------

Buildout
    The packages are contained in a buildout that allow you to build Plone with the new package installed for testing-purposes.

Locales
    The packages register a directory for locales.

Profile
    The packages contain a `Generic Setup Profile`_ that installs a browserlayer.

Setuphandler
    The packages contain a `setuphandlers.py`_ where you can add code that is executed on installing the package.

Template-Overrides
    The packages register the folder ``template_overrides`` as a directory where you can drop template-overrides using `z3c.jbot`_.

Tests
    The packages come with a test setup and some `tests`_ for installing the package.
    They also contain a `robot-test`_ for browser testing.
    The buildouts also contains a config to allow testing the package on `travis`_.



Compatibility
=============


Installation
============

Installation in a virtualenv
----------------------------

You can also install ``rasta.bob`` in a virtualenv.::

    $ pip install rasta.bob

You can also install the latest version of ``rasta.bob`` directly from GitHub::

    $ pip install -e git://github.com/Solomonic/rasta.bob.git#egg=rasta.bob

Now you can use it like this::

    $ mrbob rasta.bob:product


Use in a buildout
-----------------

::

    [buildout]
    parts += mrbob

    [mrbob]
    recipe = zc.recipe.egg
    eggs =
        mr.bob
        rasta.bob

If you want to use the latest development version from GitHub, add ``rasta.bob`` to your ``mr.developer`` source section::

    [buildout]
    extensions += mr.developer

    [sources]
    rasta.bob = git git://github.com/Solomonic/rasta.bob.git


This creates a mrbob-executeable in your bin-directory.
Call it from the ``src``-directory of your project like this.::

    $ ../bin/mrbob rasta.bob:product




.. _`mr.bob`: http://mrbob.readthedocs.org/en/latest/
.. _`travis`: http://travis-ci.org/
.. _`z3c.jbot`: https://pypi.python.org/pypi/z3c.jbot
