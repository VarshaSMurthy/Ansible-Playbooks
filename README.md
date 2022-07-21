#command to run log4j_Version.yaml playbook

ansible-playbook -i ./hosts.yml ./log4j_Version.yml  --diff --check

#execute the below command to enable the repo on servers (--check is for dry run)
ansible-playbook -i ./hosts.yml ./enableRepo.yml --diff --check
