Getting Started
===============

.. _gs_foreword:

Now that LinchPin is :doc:`installed <installation>`, this guide will walk you through the basics of using LinchPin. LinchPin is a command-line utility, a Python API, and Ansible playbooks. As this guide is intentionally brief to get you started, a more complete version can be found in the documentation links found to the left in the :doc:`index <index>`.

.. toctree::
   :maxdepth: 1

.. contents:: Topics

.. _gs_running:

Running the ``linchpin`` command
--------------------------------

.. include:: gs/linchpin_cli.rst

.. _gs_workspace:

The Workspace
-------------

.. include:: gs/workspace.rst

.. _gs_init:

Initialization (init)
`````````````````````
.. include:: includes/initialization.rst

.. _gs_resources:

Resources
---------

.. include:: includes/resources.rst

.. _gs_up:

Provisioning (up)
------------------

.. include:: gs/provisioning.rst

.. _gs_destroy:

Teardown (destroy)
------------------

.. include:: gs/teardown_destroy.rst


.. seealso::

    :doc:`cli`
        Linchpin Command-Line Interface
    :doc:`managing_resources`
        Managing Resources
    :doc:`providers`
        Available Providers
