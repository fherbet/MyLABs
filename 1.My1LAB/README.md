BUILDING NETWORK AUTOMATION SOLUTION HOMEWORKS ;-)


Diagram from EVE-NG
![Diagram](MyLAB2.png)


# [NetAutSol] Deploy Network Services (Week #4) Hands-on Exercises using Roles


## ALL IN ONE PLAY for CUST1 USING ROLES

  . ansible-playbook [CUST1_PLAY.yml](CUST1_PLAY.yml) -l CUST1 -D >> [OUTPUT](./LOGS/CUST1_PLAY.log)






# [NetAutSol] Logging and Testing (Week #5) Hands-on Exercises

## LOGGING using EXTRA VAR
  . ansible-playbook CUST1_PLAY.yml -l CUST1 -D -t [checkpostSA](1.My1LAB/roles/verify/tasks/main.yml)  -e debug_output=True  >> [OUTPUT](./LOGS/DEBUG_OUTPUT.log)



## UNIT TEST
  . ansible-playbook CUST1_PLAY.yml -l CPE1 -D -t [validate](roles/validate_bgp/tasks/main.yml) >> [OUTPUT](./LOGS/UNIT_TEST.log)
