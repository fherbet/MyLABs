Diagram from EVE-NG


![Diagram](https://github.com/fherbet/MyLABs/blob/master/2.My2LAB/MyLAB2.png)



Context :
MPLS Backbone

- PE interfaces to CUSTOMER provisionned in advance in CUST vrf
- static routes for CPEs' loopbacks provisionned in advance on PE in order to reach them from Net (ansible server)
- BGP config towards CPEs provisionned in advance in CUST vrf

== Goal is to automate configs of CPE1 and CPE2 once field tech goes on site, tests links and installs CPEs



details steps

1. from LB address, detect on which PE/interface/vlan is connected CPEx (which model/vendor is PE) and update CPEx.yml

      DONE > OK > ansible-playbook GET_DATA_PE.yml -l CPE1,CPE2 -D

      [LOGS](GET_DATA_PE.log)


2. generate basic config+final config (routing+QOS)+PE QOS/shaping

3. push basic config using napalm

4. push final config using napalm

5. run get_facts + ping tests

6. send confirmation emails



hostvars looks like [CPE1.yml](https://github.com/fherbet/MyLABs/blob/master/2.My2LAB/host_vars/CPE1.yml)
