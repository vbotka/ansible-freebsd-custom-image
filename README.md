# freebsd_custom_image

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/freebsd_custom_image)[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-custom-image.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-custom-image)[![Documentation Status](https://readthedocs.org/projects/docs/badge/?version=latest)](https://ansible-freebsd-custom-image.readthedocs.io/en/latest/)[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)[![GitHub tag](https://img.shields.io/github/tag/vbotka/ansible-freebsd-custom-image.svg)](https://github.com/vbotka/ansible-freebsd-custom-image/tags)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_custom_image/) FreeBSD. Download, mount, and customize system images.

[Documentation at readthedocs.io](https://ansible-freebsd-custom-image.readthedocs.io)

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-custom-image/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

### Roles

* [vbotka.ansible_lib](https://galaxy.ansible.com/vbotka/ansible_lib)

### Collections

* ansible.posix
* community.general


## Notes

* By default, the role is not idempotent. At least 4 tasks will be reported changed: 1) Create
  memory disk 2) Mount mdX partitions 3) Unmount mount points 4) Detach memory disk.

* Setting `bsd_cimage_umount=false` will keep the memory disk attached and partitions mounted. This
  will make the role idempotent.

* The role doesn’t support check and diff "--check --diff"


## References

- [18.9. Memory Disks - FreeBSD Handbook](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/disks-virtual.html)
- [32.3. Wireless Networking - FreeBSD Handbook](https://www.freebsd.org/doc/en_US.ISO8859-1/books/handbook/network-wireless.html)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
