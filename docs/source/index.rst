Welcome to botocore
===================

Botocore is a low-level interface to a growing number of Amazon Web
Services.  Botocore serves as the foundation for the
`AWS-CLI <https://github.com/aws/aws-cli/>`_ command line utilities.
It will also play an important role in the boto3.x project.

The botocore package is compatible with Python versions 2.6.x, Python 2.7.x,
and Python 3.3.x and higher.


.. warning::

  Botocore is currently under a developer preview, and its API is subject
  to change prior to a GA (1.0) release.  Until botocore reaches a 1.0 release,
  backwards compatibility is not guaranteed.

  If you need a stable interface, please consider using
  `boto <https://github.com/boto/boto>`__.


Contents:

.. toctree::
   :maxdepth: 2
   :glob:

   tutorial/index
   reference/*
   topics/index
   development/index


Upgrade Notes
=============

Upgrading to 0.66.0
-------------------

* The ``before-call`` and ``after-call`` events have been changed
  such that their ``model`` for the operation is sent instead of the
  ``operation`` object itself.
* The interface to waiters via ``Service.get_waiter`` has changed.
  An endpoint is now required when creating the waiter via ``get_waiter()``
  instead of when calling the waiter ``waiter.wait(endpoint, **kwargs)``.


Upgrading to 0.65.0
-------------------

* ``get_scoped_config()`` will now include credentials from the
  shared credentials file (``~/.aws/credentials``) if present.

Upgrading to 0.64.0
-------------------

* ``botocore.parameters`` has been split into several different modules
  (``validate``, ``serialize``, and ``model``).  If you were using the
  ``Operation.call`` method, you are unaffected by this change.
* A ``botocore.client`` module has been added.  This is the preferred
  interface into botocore going forward.
* Response keys that are no longer in the HTTP response are not mapped
  to default values in the response dict.
* ``ResponseMetadata`` is now always added to any successful response
* ``Errors`` has been switch from a list of errors to a single ``Error``
  key.  Also consistently populate the ``Error`` dict on errors.


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
