# Роль Lighthouse (08-ansible-04-role-lighthouse)

Описание: Роль устанавливает Lighthouse

| Field                | Value           |
|--------------------- |-----------------|
| Readme update        | 09/02/2025 |

### Defaults: Статические переменные с низким приоритетом

#### Файл: defaults/main.yml

| Var          | Type         | Value       |Required    | Title       |
|--------------|--------------|-------------|-------------|-------------|
| [lighthouse_web_user](defaults/main.yml#L2)   | str   | `www-data` |    n/a  |  n/a |
| [lighthouse_web_port](defaults/main.yml#L3)   | str   | `8888` |    n/a  |  n/a |

### Vars: Статические переменные с высоким приоритетом

#### Файл: vars/main.yml

| Var          | Type         | Value       |Required    | Title       |
|--------------|--------------|-------------|-------------|-------------|
| [lighthouse_repository](vars/main.yml#L2)   | str   | `https://github.com/VKCOM/lighthouse.git` |    n/a  |  n/a |

### Tasks: Задания

#### File: tasks/main.yml

| Name | Module | Has Conditions |
| ---- | ------ | --------- |
| Update apt cache | apt | False |
| Install required packages and dependencies | apt | False |
| Clone repository lighthouse | git | False |
| Get lighthouse config (nginx.conf) | template | False |
| Get lighthouse config (lighthouse.conf) | template | False |
| Flush handlers |  | False |

```mermaid
flowchart TD
Start
classDef block stroke:#3498db,stroke-width:2px;
classDef task stroke:#4b76bb,stroke-width:2px;
classDef includeTasks stroke:#16a085,stroke-width:2px;
classDef importTasks stroke:#34495e,stroke-width:2px;
classDef includeRole stroke:#2980b9,stroke-width:2px;
classDef importRole stroke:#699ba7,stroke-width:2px;
classDef includeVars stroke:#8e44ad,stroke-width:2px;
classDef rescue stroke:#665352,stroke-width:2px;

  Start-->|Task| Update_apt_cache0[update apt cache]:::task
  Update_apt_cache0-->|Task| Install_required_packages_and_dependencies1[install required packages and dependencies]:::task
  Install_required_packages_and_dependencies1-->|Task| Clone_repository_lighthouse2[clone repository lighthouse]:::task
  Clone_repository_lighthouse2-->|Task| Get_lighthouse_config__nginx_conf_3[get lighthouse config  nginx conf ]:::task
  Get_lighthouse_config__nginx_conf_3-->|Task| Get_lighthouse_config__lighthouse_conf_4[get lighthouse config  lighthouse conf ]:::task
  Get_lighthouse_config__lighthouse_conf_4-->|Task| Flush_handlers5[flush handlers]:::task
  Flush_handlers5-->End
```
## Сценарий

```yml
---
- hosts: localhost
  remote_user: root
  roles:
    - lighthouse-role

```

## Автор

tvm2360

#### Лицензия

MIT

#### Минимальная верия ansible

2.10

#### Платформы

- **Ubuntu**: [20.04]
