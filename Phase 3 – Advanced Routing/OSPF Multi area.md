\#router ospf 1



! Backbone

\#network 10.0.0.0 0.0.0.3 area 0   ← lien WAN Core-Edge



! Area 10

\#network 10.0.10.0 0.0.0.255 area 10

\#network 10.0.20.0 0.0.0.255 area 10

\#network 10.0.30.0 0.0.0.255 area 10

\#network 10.0.40.0 0.0.0.255 area 10



! Area 20

\#network 10.0.100.0 0.0.0.255 area 20

\#network 10.0.150.0 0.0.0.255 area 20





Sur Edge

\#router ospf 1

\#network 10.0.0.0 0.0.0.3 area 0

\#default-information originate



**(Summarization)**

Sur le Core :

router ospf 1

area 10 range 10.0.0.0 255.255.0.0

area 20 range 10.0.0.0 255.255.0.0



**Vérification**

sur EDGE:

\#show ip route ospf



Option A — Sur l’ABR (Core)

\#show ip ospf interface



Option B — Sur Edge

\*\*#\*\*show ip ospf database





Route Summarization





\#interface g0/1

&nbsp;#ip summary-address ospf 10.0.0.0 255.255.252.0  !!













































