# 📃 Role overview

## 08-ansible-04-role-lighthouse

Description: Role install lighthouse


| Field                | Value           |
|--------------------- |-----------------|
| Readme update        | 09/02/2025 |

### Defaults

**These are static variables with lower priority**

#### File: defaults/main.yml

| Var          | Type         | Value       |Required    | Title       |
|--------------|--------------|-------------|-------------|-------------|
| [lighthouse_web_user](defaults/main.yml#L2)   | str   | `www-data` |    n/a  |  n/a |
| [lighthouse_web_port](defaults/main.yml#L3)   | str   | `8888` |    n/a  |  n/a |

### Vars

**These are variables with higher priority**
#### File: vars/main.yml

| Var          | Type         | Value       |Required    | Title       |
|--------------|--------------|-------------|-------------|-------------|
| [lighthouse_repository](vars/main.yml#L2)   | str   | `https://github.com/VKCOM/lighthouse.git` |    n/a  |  n/a |

### Tasks

#### File: tasks/main.yml

| Name | Module | Has Conditions |
| ---- | ------ | --------- |
| Update apt cache | apt | False |
| Install required packages and dependencies | apt | False |
| Clone repository lighthouse | git | False |
| Get lighthouse config (nginx.conf) | template | False |
| Get lighthouse config (lighthouse.conf) | template | False |
| Flush handlers |  | False |

## Playbook

```yml
---
- hosts: localhost
  remote_user: root
  roles:
    - lighthouse-role

```

## Author Information
tvm2360

#### License

MIT

#### Minimum Ansible Version

2.1

#### Platforms

- **Ubuntu**: [20.04]
