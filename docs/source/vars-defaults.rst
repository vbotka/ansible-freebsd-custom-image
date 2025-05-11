Default variables
=================

Review the default variables in the directory ``defaults/main``. For example,

[`defaults/main/main.yml`_]

.. highlight:: yaml
    :linenothreshold: 5
.. literalinclude:: ../../defaults/main/main.yml
    :language: yaml
    :emphasize-lines: 2
    :linenos:

.. seealso::

   * The examples of the customization ``vars/main.yml.sample``

.. warning::

   * Don't make any changes to the files in *defaults/main*. The changes will be overwritten by the
     update of the role.

   * Default value of *cimage_debug_classified* is **false**. Passwords will be displayed if this
     variable is enabled.


.. _defaults/main/main.yml: https://github.com/vbotka/ansible-freebsd-custom-image/blob/master/defaults/main/main.yml
