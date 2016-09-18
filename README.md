Nexus
=========

Installs Nexus Open Source version - current installed version is **3.0.2-02**

Requirements
------------

- Java must be installed


Role Variables
--------------

```
nexus:
  version_major: 3
  version_minor: 0
  version_patch: 2
  version_build: '02'
  user: nexus
  group: nexus
  home_dir: /home/nexus

nexus_service_name: nexus
nexus_version: "{{ nexus.version_major }}.{{ nexus.version_minor }}.{{
nexus.version_patch }}-{{ nexus.version_build }}"
nexus_versioned_dir: "/opt/nexus-{{ nexus_version }}"
nexus_linked_dir: /opt/nexus
nexus_data_dir: "{{ nexus_linked_dir }}/../nexus-data"
#
https://sonatype-download.global.ssl.fastly.net/nexus/3/nexus-3.0.2-02-unix.tar.gz
nexus_download_url:
"https://sonatype-download.global.ssl.fastly.net/nexus/{{
nexus.version_major }}/nexus-{{ nexus_version }}-unix.tar.gz"
nexus_nginx_reverse_proxy: false
```

Dependencies
------------

- See requiremtns.txt at the root of this repo for required roles and
  see the example Playbook below

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: java
         - role: nexus

License
-------

Apache

Author Information
------------------

[Haggai Philip Zagury](http://www.tikalk.com/devops/haggai)
