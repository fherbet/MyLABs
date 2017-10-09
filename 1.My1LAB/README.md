BUILDING NETWORK AUTOMATION SOLUTION HOMEWORKS ;-)



LAB Up And Running !
Diagram from EVE-NG
![Diagram](MyLAB2.png)


1. EXECUTE RAW COMMANDS

ansible all -i hosts -l MGMT,CPE1,CPE2 -m raw -a "show ip route"

[RAW COMMAND OUTPUT](./LOGS/RAW_COMMAND.log)


2. 1st PLAYBOOKS

  . Execute commands
  * ansible-playbook [IOS_COMMAND.yml](IOS_COMMAND.yml) -l MGMT,CPE1,CPE2       >> [OUTPUT](./LOGS/IOS_COMMAND.log)

  * ansible-playbook [IOSXR_COMMAND.yml](IOSXR_COMMAND.yml) -l PE1,PE2       >> [OUTPUT](./LOGS/IOSXR_COMMAND.log)

  * ansible-playbook [MULTIVENDOR_COMMAND.yml](MULTIVENDOR_COMMAND.yml)    >> [OUTPUT](./LOGS/MULTIVENDOR_COMMAND.log)

  . Execute commands and save output in file
  * ansible-playbook [MULTIVENDOR_COMMAND_AND_SAVE_FILE.yml](MULTIVENDOR_COMMAND_AND_SAVE_FILE.yml)    >> [OUTPUT](./LOGS/MULTIVENDOR_COMMAND_AND_SAVE_FILE.log) / [MGMT](./configs/MGMT/MGMT_shrun.txt) / [CPE1](./configs/CPE1/CPE1_shrun.txt) / [CPE2](./configs/CPE2/CPE2_shrun.txt) / [PE1](./configs/PE1/PE1_shrun.txt) / [PE2](./configs/PE2/PE2_shrun.txt)

  * ansible-playbook [NAPALM_CLI.yml](NAPALM_CLI.yml) -l CPE1  >> [OUTPUT](./LOGS/NAPALM_CLI.log) / [CPE1](./configs/CPE1/CPE1_napalmcli.txt)

        !!!!! QUESTION!!!!!!! how to render nicely NAPALM_CLI OUTPUT ????????????????

   . JINJA2 template
  * ansible-playbook [JINJA2_SNMP_LOCATION.yml](JINJA2_SNMP_LOCATION.yml)    >> [OUTPUT](./LOGS/JINJA2_SNMP_LOCATION.log) / [CPE1](./configs/CPE1/SNMP_LOCATION.conf)

  . NAPALM_INSTALL_CONFIG
  * ansible-playbook [NAPALM_CONFIG.yml](NAPALM_CONFIG.yml) -t install_config   >> [OUTPUT](./LOGS/NAPALM_INSTALL_CONFIG.log)

  * ansible-playbook [NAPALM_CONFIG.yml](NAPALM_CONFIG.yml) -t remove_config   >> [OUTPUT](./LOGS/NAPALM_REMOVE_CONFIG.log)

  . NAPALM_GET_FACTS
  * ansible-playbook [NAPALM_GET_FACTS.yml](NAPALM_GET_FACTS.yml) >> [OUTPUT](./LOGS/NAPALM_GET_FACTS.log)
