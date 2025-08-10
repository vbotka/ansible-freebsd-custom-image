=============================================
vbotka.freebsd_custom_image 2.7 Release Notes
=============================================

.. contents:: Topics


2.7.8
=====

Release Summary
---------------

Major Changes
-------------

Minor Changes
-------------


2.7.7
=====

Release Summary
---------------
Add fn/postinstall.yml

Major Changes
-------------

Minor Changes
-------------
* Add postinstall to dictionary cimage_customize
* Add variable cimage_postinstall (default=[])
* Update debug.yml
* Update docs.


2.7.6
=====

Release Summary
---------------
Maintenance update.

Major Changes
-------------

Minor Changes
-------------
Add the collection vbotka.freebsd to the test's requirements.
Update README.


2.7.5
=====

Release Summary
---------------
Maintenance update.

Major Changes
-------------

Minor Changes
-------------
* Use the role vbotka.freebsd.lib instead of vbotka.ansible_lib
* Update docs.
* Update README


2.7.4
=====

Release Summary
---------------
Maintenance update.

Major Changes
-------------

Minor Changes
-------------
* Supported FreeBSD 13.4, 13.5, 14.2, 14.3
* Updated docs. Updated annotation templates.


2.7.3
=====

Release Summary
---------------
Add variable cimage_download_images. Remove variable cimage_mount_dir. Update
documentation.

Major Changes
-------------
* Add variable cimage_download_images lists images.
* Remove variable cimage_mount_dir. Use cimage_dir instead.

Minor Changes
-------------
* Updated documentation. Updated annotation templates.


2.7.2
=====

Release Summary
---------------
Update documentation.

Major Changes
-------------

Minor Changes
-------------
* In fn/rcconf.yml, use community.general.sysrc
* Run tasks/download.yml when cimage_download not empty
* Updated tasks/debug.yml
* Updated fn/wpasupconf.yml. Added var cimage_wpasupconf_template
  (default=wpa_supplicant.conf.j2)
* Simplified template wpa_supplicant.conf.j2. conf is list.
* Added template wpa_supplicant.conf.2.j2. conf is dictionary.

2.7.1
=====

Release Summary
---------------
Feature update.

Major Changes
-------------

Minor Changes
-------------
* Added variable cimage_download (default=true).
* Updated tasks/customize.yml. Add variable cimage_customize.
* Updated tasks/debug.yml formatting.
* Add defaults/main/authorized_keys.yml for future use.


2.7.0
=====

Release Summary
---------------
Major release.

Major Changes
-------------
* Updated meta. Support versions 13.4, 13.5, 14.2. Ansible 2.18.
* Renamed all variables bsd_cimage_* to cimage_*
* Do not run sanity always.
* Updated tasks/packages.yml. Add variable cimage_pkgng_chroot
* Run tasks/packages.yml before customize.yml
* Removed postinstall. Removed vars freebsd_install_method and
  freebsd_use_packages.
* Added vars cimage_pkgng_rootdir and cimage_pkgng_use_globs.
* Add optional variables cimage_pkgng_cached,
  cimage_pkgng_ignore_osver, and cimage_pkgng_pkgsite

Minor Changes
-------------
* Updated docs index.rst
* Updated tasks/debug.yml
* Updated defaults/main. Move configuration into separate files.
* Updated tasks/sanity.yml. Add variable cimage_sanity_quiet (default=true)
* Created cimage_dir if it does not exist.

Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
* Renamed all variables bsd_cimage_* to cimage_*
