.. figure:: _static/logo.png
    :align: center
    :width: 250px

`Turon <https://www.turon.io>`_ is a platform that allows developers and data teams to build highly performant APIs on top of their data warehouses.

This is the API documentation for Turon's official Python SDK.

Don't already have an account and Turon project? Head over to `turon.io <https://app.turon.io>`_, then return to this page.

Install
-------

Install our Python SDK using `pip <https://pip.pypa.io/en/stable/>`_:

.. code-block:: text

   pip install --upgrade turon

Usage
-----

.. code-block:: python

   from turon import Turon
   from turon.exceptions import APIException

   turon = Turon('TURON_APP_KEY', 'TURON_API_KEY')
   query = turon.query('GetUserById', user_id='582091167')

   try:
      user = query.to_dict()
   except APIException as excinfo:
      if excinfo.code == 404:
         print('User could not be found.')

API
---

.. module:: turon

This part of the documentation lists the full API reference of all public classes and functions.

Client
==========

.. autoclass:: Turon
   :members:

Query
==========

.. autoclass:: Query
   :members:

Exceptions
==========

Exceptions inherit from the base `APIException <#turon.exceptions.APIException>`_ class.

The SDK does not ship with any error handling logic. We recommend that you build out `try/except` blocks to handle errors in the way that is most appropriate for your application.

.. code-block:: python

   from turon import Turon
   from turon.exceptions import NotFound

   client = Turon('TURON_APP_KEY', 'TURON_API_KEY')
   widget = None

   try:
      widget = client.query('GetWidgetById', id='12345').to_dict()
   except NotFound:
      pass


.. automodule:: turon.exceptions
   :members:
