[![](https://img.shields.io/travis/com/ckaserer/ansible-role-desktop/master?style=flat-square)](https://travis-ci.com/ckaserer/ansible-role-desktop)
![gplv3](https://img.shields.io/badge/license-GPL%20v3.0-brightgreen.svg?style=flat-square)
![Maintenance](https://img.shields.io/maintenance/yes/2021?style=flat-square)

# ckaserer.desktop

<p align="center">
<img alt="git" src=".images/desktop.png">
</p>

---

There are two variants you can use the desktop role. Either you just install a desktop and let the users log in by themselves or you can enable autologin to a specific user by setting `autologin_user`.

Either way we need to install the latest version of the desktop ansible role from ansible galaxy via

```
ansible-galaxy install ckaserer.desktop
```

---

## Default

The playbook below installs a desktop environment on all hosts.
Alternativly you can set `hosts` to a group of ansible nodes or `localhost`.
Executing the role requires root privileges hence the additional `become: true` in the `include_role` task.

```
- hosts: all
  tasks:
    - name: "Include ckaserer.desktop"
      include_role:
        name: "ckaserer.desktop"
        apply:
          become: true
```

---

## Enable Autologin

The playbook below installs a desktop environment on all hosts and enables autologin as specified by `autologin_user`.
Executing the role requires root privileges hence the additional `become: true` in the `include_role` task.
You can set `hosts` to a group of ansible nodes or `localhost` if you want to specify a subset of nodes.

```
- hosts: all
  tasks:
    - name: "Include ckaserer.desktop"
      include_role:
        name: "ckaserer.desktop"
        apply:
          become: true
        vars:
          autologin_user: ckaserer
```    
