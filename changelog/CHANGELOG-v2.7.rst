=============================================
vbotka.freebsd_custom_image 2.7 Release Notes
=============================================

.. contents:: Topics


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


Minor Changes
-------------
* Updated docs index.rst
* Updated tasks/debug.yml
* Updated defaults/main. Move configuration into separate files.


Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
* Renamed all variables bsd_cimage_* to cimage_*
