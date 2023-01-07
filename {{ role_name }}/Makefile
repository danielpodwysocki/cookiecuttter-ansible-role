.PHONY: dev

venv/bin/activate:
	python3 -m venv venv
	. venv/bin/activate; pip install -r requirements.txt
	. venv/bin/activate; ansible-galaxy install -r requirements.yml

dev: venv/bin/activate
	source venv/bin/activate