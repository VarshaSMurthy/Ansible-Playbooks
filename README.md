#command to run log4j_Version.yaml playbook

ansible-playbook -i ./hosts.yml ./log4j_Version.yml  --diff --check
