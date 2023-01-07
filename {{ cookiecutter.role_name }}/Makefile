.PHONY: dev converge_aws clean login_aws

export AWS_VPC_SUBNET_ID=subnet-0740a1003d80202ed
# rocky9
export AWS_AMI_ID=ami-0da0f91219b2ab4c1
export AWS_REGION=eu-west-1
export AWS_INSTANCE_TYPE=t2.micro

venv/bin/activate:
	python3 -m venv venv
	. venv/bin/activate; pip install -r requirements.txt
	. venv/bin/activate; ansible-galaxy install -r requirements.yml

dev: venv/bin/activate
	source venv/bin/activate

converge_aws: venv/bin/activate
	. venv/bin/activate; molecule converge -s aws

clean: venv/bin/activate
	. venv/bin/activate; molecule destroy -s aws
	rm -rf venv

login_aws: venv/bin/activate
	. venv/bin/activate; molecule login -s aws
