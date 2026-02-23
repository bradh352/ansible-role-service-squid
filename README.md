# Squid Caching Proxy Ansible role

Author: Brad House<br/>
License: MIT<br/>
Original Repository: https://github.com/bradh352/ansible-role-service-squid

## Overview

Squid caching http proxy.  It will automatically configure squid to be aware of
Debian-like mirror filenames and efficiently cache files which are not expected
to change while only caching files that change more frequently for shorter
durations.

This will automatically determine the mount housing /var/spool/squid and
configure squid to use 80% of that mount point.  It will also configure squid
with a memory cache of 80% of the system memory as files served from memory are
about 8x faster even on fast disks (due to legacy limitations in squid).

Squid will be configured to listen on port 8080.

## Variables

- `squid_max_object_size_mb`: Maximum cachable object size.  Defaults to 8192
  (8G).
- `squid_max_object_size_mb_in_mem`: Maximum object size allowed in the memory
  cache.  Often this is smaller than the maximum object size as memory is
  limited.  Defaults to 2048 (2G).
