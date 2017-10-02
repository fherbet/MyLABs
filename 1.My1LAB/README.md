BUILDING NETWORK AUTOMATION SOLUTION HOMEWORKS ;-)



LAB Up And Running !
Diagram from EVE-NG
![Diagram](https://github.com/fherbet/MyLABs/blob/master/1.My1LAB/MyLAB2.png)


1. EXECUTE RAW COMMANDS

ansible all -i hosts -l MGMT,CPE1,CPE2 -m raw -a "show ip route"

[RAW COMMAND OUTPUT](./LOGS/RAW_COMMAND.log)


2. 1st PLAYBOOKS

  * ansible-playbook [IOS_COMMAND.yml](IOS_COMMAND.yml) -l MGMT,CPE1,CPE2       >> [OUTPUT](./LOGS/IOS_COMMAND.log)

  * ansible-playbook [IOSXR_COMMAND.yml](IOSXR_COMMAND.yml) -l PE1,PE2       >> [OUTPUT](./LOGS/IOSXR_COMMAND.log)

  * ansible-playbook [MULTIVENDOR_COMMAND.yml](MULTIVENDOR_COMMAND.yml)    >> [OUTPUT](./LOGS/MULTIVENDOR_COMMAND.log)

  * ansible-playbook [MULTIVENDOR_COMMAND_AND_SAVE_FILE.yml](MULTIVENDOR_COMMAND_AND_SAVE_FILE.yml)    >> [OUTPUT](./LOGS/MULTIVENDOR_COMMAND_AND_SAVE_FILE.log)

        [MGMT](./configs/MGMT/MGMT_shrun.txt) / [CPE1](./configs/CPE1/CPE1_shrun.txt) / [CPE2](./configs/CPE2/CPE2_shrun.txt) / [PE1](./configs/PE1/PE1_shrun.txt) / [PE2](./configs/PE2/PE2_shrun.txt)
