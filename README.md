[![CI](https://github.com/de-it-krachten/ansible-role-chrony/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-chrony/actions?query=workflow%3ACI)


# ansible-role-chrony

Install/configure chrony for time synchronization



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
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

### defaults/family-Alpine.yml
<pre><code>
# Chrony main configuration file
chrony_conf: /etc/chrony/chrony.conf

# Chrony keys
chrony_keyfile: /etc/chrony/chrony.keys

# List of packages
chrony_packages:
  - chrony

# Name of the service
chrony_service: chronyd
</pre></code>

### defaults/family-Debian.yml
<pre><code>
# Chrony main configuration file
chrony_conf: /etc/chrony/chrony.conf

# Chrony keys
chrony_keyfile: /etc/chrony/chrony.keys

# List of packages
chrony_packages:
  - chrony

# Name of the service
chrony_service: chrony
</pre></code>

### defaults/family-RedHat.yml
<pre><code>
# Chrony main configuration file
chrony_conf: /etc/chrony.conf

# Chrony keys
chrony_keyfile: /etc/chrony.keys

# List of packages
chrony_packages:
  - chrony

# Name of the service
chrony_service: chronyd
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'chrony'
  hosts: all
  become: "yes"
  tasks:
    - name: Include role 'chrony'
      ansible.builtin.include_role:
        name: chrony
</pre></code>
