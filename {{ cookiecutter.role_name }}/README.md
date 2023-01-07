# {{ cookiecutter.role_namespace }}.{{ cookiecutter.role_name }}

A brief description of the role goes here.

## Requirements

All outside requirements.

Note: all pip requirements should be handled in the role's `requirements.txt` file.
All module and role dependencies should be handled in the role's requirements.yml file and included in the `meta/main.yml` file.

## Role Variables

| Name | Default value | Description | Required |
|------|---------------|-------------|:--------:|


## Example Playbook
```

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }
      vars:
        var1: value1
        var2: value2
```

## Licensing and authorship

{{ cookiecutter.license }}
Author: {{ cookiecutter.author_firstname }} {{ cookiecutter.author_lastname }} ({{ cookiecutter.author_contact_info }})
