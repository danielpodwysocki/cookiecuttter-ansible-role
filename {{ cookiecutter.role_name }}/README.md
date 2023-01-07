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

## Testing and development

This repository uses [Molecule](https://molecule.readthedocs.io/en/latest/) for testing and development.
It abstracts some of the key commands behind a Makefile, so you can run the following commands:

```
make converge_aws # Create an EC2 instance and run the role on it
make converge_vagrant # Create a Vagrant VM and run the role on it
make test_aws # Run the role and tests on an existing EC2 instance
make test_vagrant # Run the role and tests on an existing Vagrant VM
make destroy_aws # clean up the EC2 instance
make destroy_vagrant # clean up the Vagrant VM
make clean # clean up the Vagrant VM and the EC2 instance, nuke the virtualenv
```


To use EC2, you need the AWS CLI configured and to specify some settings in the Makefile.
You can find them at the top:
```
# Subnet ID to create the instance in
export AWS_VPC_SUBNET_ID=subnet-0740a1003d80202ed
# AMI ID - in this case, Rocky Linux 9
export AWS_AMI_ID=ami-0da0f91219b2ab4c1
# Region to create the instance in
export AWS_REGION=eu-west-1
# Instance type to create
export AWS_INSTANCE_TYPE=t2.micro
```

For vagrant, you need Vagrant and virtualbox installed.
You can find the settings for vagrant in the Makefile as well:
```
# what image to use for vagrant
export VAGRANT_DEFAULT_BOX=generic/rocky9
```

If you want to run molecule commands freely, you can use the `molecule` command directly.

```
source venv/bin/activate
export AWS_VPC_SUBNET_ID=subnet-0740a1003d80202ed
# rocky9
export AWS_AMI_ID=ami-0da0f91219b2ab4c1
export AWS_REGION=eu-west-1
export AWS_INSTANCE_TYPE=t2.micro
export VAGRANT_DEFAULT_BOX=generic/rocky9


molecule <your command> -s <aws|vagrant>
```


## Licensing and authorship

{{ cookiecutter.license }}
Author: {{ cookiecutter.author_firstname }} {{ cookiecutter.author_lastname }} ({{ cookiecutter.author_contact_info }})
