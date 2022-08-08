# Ansible Collection - nginx.nginx_controller

# This repository has been archived. There will likely be no further development on the project and security vulnerabilities may be unaddressed. #

This collection contains all the roles maintained to support NGINX Controller 3.0 and later. The collection can be found on [Ansible Galaxy](https://galaxy.ansible.com/nginxinc/nginx_controller).

It includes:


| Ansible Galaxy | GitHub |
| ------ | ------ |
| [nginxinc.nginx_controller_install](https://galaxy.ansible.com/nginxinc/nginx_controller_install) | [ansible-role-nginx-controller-install](https://github.com/nginxinc/ansible-role-nginx-controller-install) <br/>![molecule workflow](https://github.com/nginxinc/ansible_role_nginx_controller_install/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_license](https://galaxy.ansible.com/nginxinc/nginx_controller_license) | [ansible-role-nginx-controller-license](https://github.com/nginxinc/ansible-role-nginx-controller-license) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-license/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_generate_token](https://galaxy.ansible.com/nginxinc/nginx_controller_generate_token) | [ansible-role-nginx-controller-generate-token](https://github.com/nginxinc/ansible-role-nginx-controller-generate-token) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-generate-token/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_agent](https://galaxy.ansible.com/nginxinc/nginx_controller_agent) | [ansible-role-nginx-controller-agent](https://github.com/nginxinc/ansible-role-nginx-controller-agent) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-agent/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_certificate](https://galaxy.ansible.com/nginxinc/nginx_controller_certificate) | [ansible-role-nginx-controller-certificate](https://github.com/nginxinc/ansible-role-nginx-controller-certificate) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-certificate/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_gateway](https://galaxy.ansible.com/nginxinc/nginx_controller_gateway) | [ansible-role-nginx-controller-gateway](https://github.com/nginxinc/ansible-role-nginx-controller-gateway) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-gateway/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_application](https://galaxy.ansible.com/nginxinc/nginx_controller_application) | [ansible-role-nginx_controller_application](https://github.com/nginxinc/ansible-role-nginx_controller_application) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_application/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_component](https://galaxy.ansible.com/nginxinc/nginx_controller_component) | [ansible-role-nginx-controller-component](https://github.com/nginxinc/ansible-role-nginx-controller-component) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx-controller-component/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_location](https://galaxy.ansible.com/nginxinc/nginx_controller_location) | [ansible-role-nginx_controller_location](https://github.com/nginxinc/ansible-role-nginx_controller_location) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_location/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_environment](https://galaxy.ansible.com/nginxinc/nginx_controller_environment) | [ansible-role-nginx_controller_environment](https://github.com/nginxinc/ansible-role-nginx_controller_environment) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_environment/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_user](https://galaxy.ansible.com/nginxinc/nginx_controller_user) | [ansible-role-nginx_controller_user](https://github.com/nginxinc/ansible-role-nginx_controller_user) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_user/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx_controller_user_role](https://galaxy.ansible.com/nginxinc/nginx_controller_user_role) | [ansible-role-nginx_controller_user_role](https://github.com/nginxinc/ansible-role-nginx_controller_user_role) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_user_role/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.ansible_role_nginx_controller_api_definition_import](https://galaxy.ansible.com/nginxinc/ansible_role_nginx_controller_api_definition_import) | [ansible-role-nginx_controller_api_definition_import](https://github.com/nginxinc/ansible-role-nginx_controller_api_definition_import) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_api_definition_import/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.ansible_role_nginx_controller_publish_api](https://galaxy.ansible.com/nginxinc/ansible_role_nginx_controller_publish_api) | [ansible-role-nginx_controller_publish_api](https://github.com/nginxinc/ansible-role-nginx_controller_publish_api) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx_controller_publish_api/actions/workflows/molecule.yml/badge.svg) |
| [nginxinc.nginx](https://galaxy.ansible.com/nginxinc/nginx) | [ansible-role-nginx](https://github.com/nginxinc/ansible-role-nginx) <br/>![molecule workflow](https://github.com/nginxinc/ansible-role-nginx/actions/workflows/molecule.yml/badge.svg) |


Experimental roles not yet published to Galaxy:
| GitHub |
| -------|
| [ansible-role-nginx_controller_integration](https://github.com/nginxinc/ansible-role-nginx_controller_integration) |
| [ansible-role-nginx_controller_forwarder](https://github.com/nginxinc/ansible-role-nginx_controller_forwarder) |



## Use guidelines

Install this collection locally:

ansible-galaxy collection install nginxinc.nginx_controller -p ./collections

Then you can use the roles from the collection in your playbooks / plays:

```yaml
---
- hosts: nginx_instances

    collections:
    - nginxinc.nginx_controller

    roles:
    - role: nginx
        vars:
        nginx_enable: true
        nginx_start: true
        nginx_type: plus

    - role: nginx_controller_generate_token
        vars:
          nginx_controller_fqdn: controller.example.local
          nginx_controller_user_email: user@example.local
          nginx_controller_user_password: Secur3P@ssw0rd

    - role: nginx_controller_agent
        vars:
          nginx_controller_fqdn: controller.example.local
```

> It is possible to be more explicit. For example a fully-qualified role name such as `nginxinc.nginx_controller.nginx` instead of `nginx` is helpful if you maintain a different `nginx` role on your local workstation at a different local path.

Reference the Collection at the start of a playbook:

```yaml
---
- hosts: localhost
  gather_facts: no
  collections:
  - nginxinc.nginx_controller

  tasks:
  - name: load the vars.yaml 
    include_vars: "{{ playbook_dir }}/vars.yaml"
```

Using requirements.yaml

<playbook folder>/collections/requirements.yml

```yaml
---
collections:
- name: nginxinc.nginx_controller
  #version: 3.3.1
```
## Author

[Brian Ehlert](https://github.com/brianehlert)

[Daniel Edgar](https://github.com/aknot242)
