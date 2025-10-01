# Squid Caching Proxy Ansible role

Author: Brad House<br/>
License: MIT<br/>
Original Repository: https://github.com/bradh352/ansible-role-service-squid

## Overview

Squid caching http proxy.  This role takes no variables.  It will automatically
configure squid to be aware of Debian-like mirror filenames and efficiently
cache files which are not expected to change while only caching files that
change more frequently for shorter durations.

This will automatically determine the mount housing /var/spool/squid and
configure squid to use 80% of that mount point.

Squid will be configured to listen on port 8080.
