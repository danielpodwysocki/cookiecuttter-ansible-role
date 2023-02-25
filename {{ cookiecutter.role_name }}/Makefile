.PHONY: dev converge_aws clean login_aws test_aws destroy_aws converge_vagrant test_vagrant destroy_vagrant docs


export AWS_VPC_SUBNET_ID=subnet-0740a1003d80202ed
# rocky9
export AWS_AMI_ID=ami-0da0f91219b2ab4c1
export AWS_REGION=eu-west-1
export AWS_INSTANCE_TYPE=t2.micro
export VAGRANT_DEFAULT_BOX=generic/rocky9

docs: venv/bin/activate
	@echo "Building docs"
	@venv/bin/ansible-doctor

venv/bin/activate:
	python3 -m venv venv
	. venv/bin/activate; pip install -r requirements.txt
	. venv/bin/activate; ansible-galaxy install -r requirements.yml

converge_aws: venv/bin/activate
	. venv/bin/activate; molecule converge -s aws

test_aws: venv/bin/activate
	. venv/bin/activate; molecule test -s aws

destroy_aws: venv/bin/activate
	. venv/bin/activate; molecule destroy -s aws

converge_vagrant: venv/bin/activate
	. venv/bin/activate; molecule converge -s vagrant

test_vagrant: venv/bin/activate
	. venv/bin/activate; molecule test -s vagrant

destroy_vagrant: venv/bin/activate
	. venv/bin/activate; molecule destroy -s vagrant

clean: venv/bin/activate
	. venv/bin/activate; molecule destroy -s aws
	rm -rf venv

login_aws: venv/bin/activate
	. venv/bin/activate; molecule login -s aws

login_vagrant: venv/bin/activate
	. venv/bin/activate; molecule login -s vagrant
