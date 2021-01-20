.. _ug_example_001:

Configure wifi by config_light
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

To configure the image, it's possible to use Ansible role `vbotka.config_light
<https://galaxy.ansible.com/vbotka/config_light>`_, instead of the :ref:`ug_tasks`. This example
configures exactly the same parameters of the wireless network as the :ref:`qg`. The playbook
``pb-wifi-basic.yml`` created in the :ref:`qg` will be used to attach a memory disk and mount the
partition.

* Current directory ::

    shell> ls -1
    conf-light
    hosts
    pb-wifi-basic-cl.yml
    pb-wifi-basic.yml

* Install the role ``vbotka.config_light`` ::

    shell> ansible-galaxy install vbotka.freebsd_config_light


* Create the playbook ``pb-wifi-basic-cl.yml`` for single host images.example.com (1). Configure connection
  (3-4) and privilege escalation (5-7). Configure the directory (10) with the configuration files
  and reuse the configuration (12-17) already prepared in :ref:`qg` (19-50).

.. literalinclude:: ../../contrib/playbook/pb-wifi-basic-cl.yml
  :caption: [`contrib/playbook/pb-wifi-basic-cl.yml <https://raw.githubusercontent.com/vbotka/ansible-freebsd-custom-image/master/contrib/playbook/pb-wifi-basic-cl.yml>`_]
  :lines: 27-80
  :language: yaml
  :emphasize-lines: 1,3-7,10,12-17
  :linenos:


* Create the configuration files in the directory ``cl_dird`` ::

    shell> tree conf-light/
    conf-light/
    ├── files.d
    │   ├── loaderconf.yml
    │   ├── rcconf.yml
    │   └── wpasupconf.yml
    ├── handlers.d
    ├── packages.d
    ├── services.d
    └── states.d
        └── wpasupconf.yml

.. seealso:: How to configure `Files in vbotka.config_light <https://ansible-config-light.readthedocs.io/en/latest/guide.html#files>`_

.. literalinclude:: ../../contrib/example-wifi-basic-cl/conf-light/files.d/loaderconf.yml
  :caption: [contrib/example-wifi-basic-cl/conf-light/files.d/loaderconf.yml]
  :language: yaml
  :emphasize-lines: 3,9
  :linenos:

.. seealso:: `template loader.conf.j2 <https://raw.githubusercontent.com/vbotka/ansible-config-light/master/templates/loader.conf.j2>`_

.. literalinclude:: ../../contrib/example-wifi-basic-cl/conf-light/files.d/rcconf.yml
  :caption: [contrib/example-wifi-basic-cl/conf-light/files.d/rcconf.yml]
  :language: yaml
  :emphasize-lines: 3,8
  :linenos:

.. literalinclude:: ../../contrib/example-wifi-basic-cl/conf-light/files.d/wpasupconf.yml
  :caption: [contrib/example-wifi-basic-cl/conf-light/files.d/wpasupconf.yml]
  :language: yaml
  :emphasize-lines: 3,9
  :linenos:

.. seealso:: `template wpa_supplicant.conf.wlan0.j2 <https://raw.githubusercontent.com/vbotka/ansible-config-light/master/templates/wpa_supplicant.conf.wlan0.j2>`_

.. literalinclude:: ../../contrib/example-wifi-basic-cl/conf-light/states.d/wpasupconf.yml
  :caption: [contrib/example-wifi-basic-cl/conf-light/states.d/wpasupconf.yml]
  :language: yaml
  :emphasize-lines: 2,4,5
  :linenos:


* Create the inventory. Change the IP adress (2) and fit the paths to Python (8) and Perl (9) if
  necessary

.. code-block:: sh
   :emphasize-lines: 2,8-9
   :linenos:

    shell> cat hosts
    images.example.com ansible_host=<ip-address>

    [images]
    images.example.com

    [images:vars]
    ansible_python_interpreter=/usr/local/bin/python3.7
    ansible_perl_interpreter=/usr/local/bin/perl


* Mount the image using the playbook prepared in :ref:`qg` ::

   shell> ansible-playbook pb-wifi-basic.yml -t bsd_cimage_mount


* Test syntax ::

    shell> ansible-playbook pb-wifi-basic-cl.yml --syntax-check


* See what variables will be included ::

    shell> ansible-playbook pb-wifi-basic-cl.yml -t cl_debug -e cl_debug=true


* Run the playbook ::

    shell> ansible-playbook pb-wifi-basic-cl.yml


* Umount the partition and detach the memory disk ::

   shell> ansible-playbook pb-wifi-basic.yml -t bsd_cimage_umount


* Write the customized image to a disk and boot the system. See details in :ref:`qg`.
