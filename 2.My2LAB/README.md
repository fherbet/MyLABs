Diagram from EVE-NG


![Diagram](https://github.com/fherbet/MyLABs/blob/master/2.My2LAB/MyLAB2.png)



Context :
MPLS Backbone

- PE interfaces to CUSTOMER provisionned in advance in CUST vrf
- static routes for CPEs' loopbacks provisionned in advance on PE in order to reach them from Net (ansible server)
- BGP config towards CPEs provisionned in advance in CUST vrf

== Goal is to automate configs of CPE1 adn CPE2 once field tech goes on site, tests links and installs CPEs



details steps

1. from LB address, detect on which PE/interface/vlan is connected CPEx (which model/vendor is PE) and update CPEx.yml

2. generate basic config+final config (routing+QOS)+PE QOS/shaping

3. push basic config using napalm

4. push final config using napalm

5. run get_facts + ping tests

6. send confirmation emails



hostvars contains

---
ORDER: 'CPE1'
RELATED_ORDER: 'CPE2'
SITE_NAME_ALIAS: SITE1-PRIMARY
SITE_ID: 1
REGION: REGION
COUNTRY: SPAIN
CITY: BARCELONA
STREET: PLAYA
CPE_MODEL: IOSv
COLT_HOSTNAME: CPE1
COLT_LB:
    0:
        IP: 10.255.1.11/32
CUST_HOSTNAME: CUST_CPE1
CUST_LB:
    0:
        ID: 1
        IP: 1.1.1.1/32
        SUBVPN: SPAIN
ROLE: Spoke
PROVIDER: TELEFONICA
PROVIDER_PRODUCT: SpeedAcceSS bridge 4MB
LINK_ID: MAD/MAD/IA-194201
ACCESS_BW: 10 Mbps
SERVICE_BW: 4 Mbps
SAR:
SAR_INT: 0
GRT_SUBVPN: SPAIN
GLOBAL_ROUTING_OPTION: ROUTING_EU
SUBVPN:
    0:
        NAME: SPAIN
        STATUS: Yes
        BW: 4 Mbps
        PE_VLAN: 0
        QOS_PROFILE: 4M
        WAN:
            0:
                INT:
                VLAN: 0
                IP: 10.253.1.2/32
        LAN:
            0:
                INT:
                VLAN: 0
                MEDIA: RJ45
                SPEED: auto
                DUPLEX: auto
                IP: 10.223.1.252 / 255.255.255.0
                IP_HELPER:
                VIP:
                    0:
                        ID: 1
                        IP: 10.223.1.254 / 255.255.255.0
        B2B:
            0:
                INT: GigabitEthernet0/2
                VLAN: 3
                MEDIA: RJ45
                SPEED: auto
                DUPLEX: auto
                IP: 10.255.80.17/30
