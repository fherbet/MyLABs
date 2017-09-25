Diagram from EVE-NG

https://github.com/fherbet/MyLABs/blob/master/2.My2LAB/MyLAB2.png


Context :
MPLS Backbone

PE interfaces to CUSTOMER provisionned in advance in CUST vrf
static routes for CPEs' loopbacks provisionned in advance on PE in order to reach them from Net (ansible server)
BGP config towards CPEs provisionned in advance in CUST vrf

== Goal is to automate configs of CPE1 adn CPE2 once field tech goes on site, tests links and installs CPEs



details steps

hostvars contains 
