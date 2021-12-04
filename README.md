[![CI](https://github.com/de-it-krachten/ansible-role-chrony/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-chrony/actions?query=workflow%3ACI)


# ansible-role-chrony

Installs/configes chrony as NTP client


Platforms
--------------

Supported platforms

- CentOS 7
- CentOS 8
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Debian 10 (Buster)



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

- name: Converge
  hosts: all
  tasks:

    - name: "Include role 'ansible-role-chrony'"
      include_role:
        name: "ansible-role-chrony"
</pre></code>
