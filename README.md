#command to run log4j_Version.yaml playbook

ansible-playbook -i ./hosts.yml ./log4j_Version.yml  --diff --check

#execute the below command to enable the repo on servers (--check is for dry run)
ansible-playbook -i ./hosts.yml ./enableRepo.yml --diff --check

#execute the below command to get server details
ansible-playbook -i inventories/hosts.yml serverDetails.yaml --limit all

#To get the list of all unreachable servers
ansible -i inventories/hosts.yml -m ping all | grep UNREACHABLE >> unavail.txt
cat unavail.txt | awk -F '|' '{print $1 }' >> unReachableHost.txt

#To get all the Reachable, up and active servers
ansible-playbook -i inventories/hosts.yml reachableServer.yaml --limit all
