[![CI](https://github.com/de-it-krachten/ansible-role-chrony/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-chrony/actions?query=workflow%3ACI)


# ansible-role-chrony

Installs/configes chrony as NTP client

Platforms
--------------

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- CentOS 7
- RockyLinux 8
- AlmaLinux 8<sup>1</sup>
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms

Role Variables
--------------
<pre><code>
# Chrony configuration template
chrony_conf_template: chrony.conf.j2

# NTP servers to connect to
chrony_servers:
  - 0.nl.pool.ntp.org
  - 1.nl.pool.ntp.org
  - 2.nl.pool.ntp.org
  - 3.nl.pool.ntp.org

# Chrony makestep arguments
chrony_makestep: '10 3'
</pre></code>


Example Playbook
----------------

<pre><code>
- name: sample playbook for role 'chrony'
  hosts: all
  vars:
  tasks:
    - name: Include role 'chrony'
      include_role:
        name: chrony
</pre></code>
