# Router 0
```bash
<pre>
Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#
Router(config)#inter
Router(config)#interface g0/2
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.62 255.255.255.192
Router(config-if)#
Router(config-if)#
Router(config-if)#interface g0/0
Router(config-if)#ip a 
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.129 255.255.255.252
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#ip address 192.168.1.141 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#exit
Router(config)#
Router(config)#ip route
Router(config)#ip route 192.168.1.64 255.255.255.192
</pre>
```

# Router 1
```bash
<pre>
  Router>
Router>
Router>en
Router#
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#
Router(config)#inter
Router(config)#interface g0/0
Router(config-if)#
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.138 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.142 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#end
Router#
</pre>
```

# Router 2
```bash
<pre>
  Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#iner
Router(config)#inter
Router(config)#interface g0/0
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.130 255.255.255.252
Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#
Router(config-if)#no shut
Router(config-if)#no shutdown 

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.133 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#exit
Router(config)#
Router(config)#
Router(config)#ip rou
Router(config)#ip route 192.168.1.64 255.255.255.192 192.168.1.134
Router(config)#
Router(config)#
Router(config)#
Router(config)#ip rou
Router(config)#ip route 192.168.1.0 255.255.255.192 192.168.1.129
Router(config)#
Router(config)#do show ip inter
Router(config)#do show ip inter bri
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     192.168.1.130   YES manual up                    up 
GigabitEthernet0/1     192.168.1.133   YES manual up                    up 
GigabitEthernet0/2     unassigned      YES unset  administratively down down 
Vlan1                  unassigned      YES unset  administratively down down
Router(config)#do show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     192.168.1.0/24 is variably subnetted, 6 subnets, 3 masks
S       192.168.1.0/26 [1/0] via 192.168.1.129
S       192.168.1.64/26 [1/0] via 192.168.1.134
C       192.168.1.128/30 is directly connected, GigabitEthernet0/0
L       192.168.1.130/32 is directly connected, GigabitEthernet0/0
C       192.168.1.132/30 is directly connected, GigabitEthernet0/1
L       192.168.1.133/32 is directly connected, GigabitEthernet0/1

Router(config)#

</pre>
```

# Router 3
```bash
<pre>
  Router>
Router>en
Router#
Router#conf t 
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#inter
Router(config)#interface g0/0
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.134 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 192.168.1.137 255.255.255.252
Router(config-if)#
Router(config-if)#interface g0/2
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

Router(config-if)#
Router(config-if)#ip ad
Router(config-if)#ip address 192.168.1.126 255.255.255.192
Router(config-if)#
Router(config-if)#
Router(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#exit
Router(config)#
Router(config)#
Router(config)#ip route 192.168.1.0 255.255.255.192 192.168.1.133
Router(config)#
Router(config)#
Router(config)#do show ip inter
Router(config)#do show ip inter br
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     192.168.1.134   YES manual up                    up 
GigabitEthernet0/1     192.168.1.137   YES manual up                    up 
GigabitEthernet0/2     192.168.1.126   YES manual up                    up 
Vlan1                  unassigned      YES unset  administratively down down
Router(config)#

</pre>
```
