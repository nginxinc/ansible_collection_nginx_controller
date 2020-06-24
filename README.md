# Ansible Collection - nginx.nginx_controller

This collection contains all the roles maintained to support NGINX Controller 3.0 and later.

It includes:

- [nginxinc.nginx_controller_install](https://galaxy.ansible.com/nginxinc/nginx_controller_install)
- [nginxinc.nginx_controller_license](https://galaxy.ansible.com/nginxinc/nginx_controller_license)
- [nginxinc.nginx_controller_generate_token](https://galaxy.ansible.com/nginxinc/nginx_controller_generate_token)
- [nginxinc.nginx_controller_agent](https://galaxy.ansible.com/nginxinc/nginx_controller_agent)
- [nginxinc.nginx_controller_certificate](https://galaxy.ansible.com/nginxinc/nginx_controller_certificate)
- [nginxinc.nginx_controller_gateway](https://galaxy.ansible.com/nginxinc/nginx_controller_gateway)
- [nginxinc.nginx_controller_application](https://galaxy.ansible.com/nginxinc/nginx_controller_application)
- [nginxinc.nginx_controller_component](https://galaxy.ansible.com/nginxinc/nginx_controller_component)
- [nginxinc.nginx_controller_location](https://github.com/nginxinc/ansible-role-nginx_controller_location)
- [nginxinc.nginx_controller_environment](https://github.com/nginxinc/ansible-role-nginx_controller_environment)
- [nginxinc.nginx](https://galaxy.ansible.com/nginxinc/nginx)

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
