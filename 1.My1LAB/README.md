BUILDING NETWORK AUTOMATION SOLUTION HOMEWORKS ;-)



LAB Up And Running !
Diagram from EVE-NG
![Diagram](https://github.com/fherbet/MyLABs/blob/master/1.My1LAB/MyLAB2.png)


1. EXECUTE RAW COMMANDS

ansible all -i hosts -l MGMT,CPE1,CPE2 -m raw -a "show ip route"

[RAW COMMAND OUTPUT](./LOGS/RAW_COMMAND.log)


2. 1st PLAYBOOKS

  * ansible-playbook [IOS_COMMAND.yml](IOS_COMMAND.yml) -l MGMT,CPE1,CPE2 >>>>>>>>>> [OUTPUT](./LOGS/IOS_COMMAND.log)

  * ansible-playbook [IOSXR_COMMAND.yml](IOSXR_COMMAND.yml) -l PE1,PE2

  * ansible-playbook MULTIVENDOR_COMMAND.yml
