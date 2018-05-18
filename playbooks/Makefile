SHELL=/bin/bash

# Confirm Ansible is installed.
CHECK := $(shell command -v ansible-playbook 2> /dev/null)
INVENTORY ?= 'inventory/inventory.yml'
PLAYBOOK ?= 'site.yml'

.PHONY: all

# Default target, build *and* run tests
all:
ifndef CHECK
	$(error Ansible is not installed. Install Ansible with 'yum update -y && yum install -y ansible')
endif
	#ansible -m raw -a "pkg install -y python27" firewall.lan -i inventory/inventory.yml --ask-pass
	ansible-playbook $(PLAYBOOK) -i $(INVENTORY) --ask-pass
