.. code-block:: bash
   :emphasize-lines: 1

   shell> ansible-playbook playbook.yml --list-tags
   
   playbook: playbook.yml

   play #1 (images.example.com): images.example.com TAGS: []
      TASK TAGS: [always, bsd_cimage_customize, bsd_cimage_debug,
      bsd_cimage_download, bsd_cimage_loaderconf, bsd_cimage_mdconfig,
      bsd_cimage_mount, bsd_cimage_mount_points, bsd_cimage_packages,
      bsd_cimage_rcconf, bsd_cimage_sanity, bsd_cimage_umount,
      bsd_cimage_unpack, bsd_cimage_wpasupconf]
