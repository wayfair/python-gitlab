#######
Runners
#######

Runners are external process used to run CI jobs. They are deployed by the
administrator and registered to the GitLab instance.

Shared runners are available for all projects. Specific runners are enabled for
a list of projects.

Global runners (admin)
======================

* Object class: :class:`~gitlab.objects.Runner`
* Manager objects: :attr:`gitlab.Gitlab.runners`

Examples
--------

Use the ``list()`` and ``all()`` methods to list runners.

Both methods accept a ``scope`` parameter to filter the list. Allowed values
for this parameter are:

* ``active``
* ``paused``
* ``online``
* ``specific`` (``all()`` only)
* ``shared`` (``all()`` only)

.. note::

   The returned objects hold minimal information about the runners. Use the
   ``get()`` method to retrieve detail about a runner.

.. literalinclude:: runners.py
   :start-after: # list
   :end-before: # end list

Get a runner's detail:

.. literalinclude:: runners.py
   :start-after: # get
   :end-before: # end get

Update a runner:

.. literalinclude:: runners.py
   :start-after: # update
   :end-before: # end update

Remove a runner:

.. literalinclude:: runners.py
   :start-after: # delete
   :end-before: # end delete

Project runners
===============

* Object class: :class:`~gitlab.objects.ProjectRunner`
* Manager objects: :attr:`gitlab.Gitlab.runners`,
  :attr:`gitlab.Gitlab.Project.runners`

Examples
--------

List the runners for a project:

.. literalinclude:: runners.py
   :start-after: # project list
   :end-before: # end project list

Enable a specific runner for a project:

.. literalinclude:: runners.py
   :start-after: # project enable
   :end-before: # end project enable

Disable a specific runner for a project:

.. literalinclude:: runners.py
   :start-after: # project disable
   :end-before: # end project disable
