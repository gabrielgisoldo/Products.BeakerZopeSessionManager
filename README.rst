Introduction
============

``Products.BeakerZopeSessionManager`` is a replacement for the default Zope 4
session implementation.  It uses `Beaker`_ as a backend (via `collective.beaker`_)
and adapts the Beaker session to provide the same interface as a normal Zope
session.

Beaker is a better alternative to the default session implementation for several
reasons:

 * The Zope session implementation does not perform well in high-write scenarios.
 * Beaker provides better flexibility in where session data is actually stored.
 * Beaker is used and maintained outside of the Zope ecosystem.

.. Note::
   If you are developing a product that needs sessions but are not already
   using Zope sessions, you should probably just use collective.beaker
   directly. This product is meant for use with existing add-ons that already
   use Zope sessions (i.e. request.SESSION).

.. _`Beaker`: http://beaker.groovie.org/
.. _`collective.beaker`: http://pypi.python.org/pypi/collective.beaker

Installation
------------

Include the line ``<include package="collective.beaker" />`` in yout site.zcml

Edit the file `lib/python3.7/site-packages/Zope2/Startup/serve.py` inside your virtual env.

Notes
-----

* Beaker does not automatically clean up old sessions, so you may want to set
  up a cron job to take care of this.

Contributors
============

* Gabriel Gisoldo [gabrielgisoldo]

.. include:: CHANGES.rst
