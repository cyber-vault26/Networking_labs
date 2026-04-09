
# Switch1
```bash
Switch>
Switch>en
Switch#
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/1 (1), with Switch GigabitEthernet0/1 (999).

Switch#con ft
% Ambiguous command: "con ft"
Switch#
Switch#
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#
Switch(config)#
Switch(config)#inter
Switch(config)#interface F0/1-2
                            ^
% Invalid input detected at '^' marker.
	
Switch(config)#interface RANGE F0/1-2
Switch(config-if-range)#sw
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#sw
Switch(config-if-range)#switchport access vlan 10
% Access VLAN does not exist. Creating vlan 10
Switch(config-if-range)#
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/1 (1), with Switch GigabitEthernet0/1 (999).

Switch(config-if-range)#
Switch(config-if-range)#interface RANGE F0/3-4
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 20
% Access VLAN does not exist. Creating vlan 20
Switch(config-if-range)#
Switch(config-if-range)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/1
Switch(config-if)#sw
Switch(config-if)#switchport mode tr
Switch(config-if)#switchport mode trunk 
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport trunk allowed vlan 10,20
Switch(config-if)#switchport
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/1 (1), with Switch GigabitEthernet0switchport trunk allowed vlan 10,20
Switch(config-if)#
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport trun
Switch(config-if)#switchport trunk native
tch(config-if)#switchport trunk native vlan 999
Switch(config-if)#
```
# Switch0
```bash
Switch>
Switch>en
Switch#
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#
Switch(config)#
Switch(config)#inter
Switch(config)#interface f0/1
Switch(config-if)#
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport mode acc
Switch(config-if)#switchport mode access 
Switch(config-if)#sw
Switch(config-if)#switchport acc
Switch(config-if)#switchport access vlan 30
% Access VLAN does not exist. Creating vlan 30
Switch(config-if)#
Switch(config-if)#
Switch(config-if)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface f0/3-4
                            ^
% Invalid input detected at '^' marker.
	
Switch(config)#interface range f0/3-4
Switch(config-if-range)#sw
Switch(config-if-range)#switchport mode 
Switch(config-if-range)#switchport mode acc
Switch(config-if-range)#switchport mode access 
Switch(config-if-range)#sw
Switch(config-if-range)#switchport access vlan 20
% Access VLAN does not exist. Creating vlan 20
Switch(config-if-range)#
Switch(config-if-range)#interface range f0/5-6
Switch(config-if-range)#switchport mode access 
Switch(config-if-range)#switchport access vlan 10
% Access VLAN does not exist. Creating vlan 10
Switch(config-if-range)#
Switch(config-if-range)#
Switch(config-if-range)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/1
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport mode tr
Switch(config-if)#switchport mode trunk 

Switch(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport tru
Switch(config-if)#switchport trunk allowed vlan 10,20,30
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport trunk nat
Switch(config-if)#switchport trunk native vlan 999
Switch(config-if)#
Switch(config-if)#
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/1 (999), with Switch GigabitEthernet0/1 (1).

%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/1 (999), with Switch GigabitEthernet0/1 (1).

Switch(config-if)#
Switch(config-if)#
Switch(config-if)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/2
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport mode trunk
Switch(config-if)#
Switch(config-if)#sw
Switch(config-if)#switchport trunk
Switch(config-if)#switchport trunk allowed vlan 10,20,30
```
# Router0
```bash
Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#interface
Router(config)#interface g0/2
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

Router(config-if)#inter
Router(config-if)#interface g0/2.10
Router(config-subif)#
%LINK-3-UPDOWN: Interface GigabitEthernet0/2.10, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2.10, changed state to up

Router(config-subif)#en
Router(config-subif)#encapsulation dot
Router(config-subif)#encapsulation dot1Q 10
Router(config-subif)#ip add
Router(config-subif)#ip address 172.16.1.254 255.255.255.0
Router(config-subif)#interface g0/2.20
Router(config-subif)#
%LINK-3-UPDOWN: Interface GigabitEthernet0/2.20, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2.20, changed state to up

Router(config-subif)#encapsulation dot1Q 20
Router(config-subif)#ip add
Router(config-subif)#ip address 172.16.1.126 255.255.255.128
% 172.16.1.0 overlaps with GigabitEthernet0/2.10
Router(config-subif)#interface g0/2.10
Router(config-subif)#no ip address 172.16.1.254 255.255.255.0
Router(config-subif)#ip address 172.16.0.254 255.255.255.0
Router(config-subif)#
Router(config-subif)#interface g0/2.20
Router(config-subif)#ip address 172.16.1.126 255.255.255.128
Router(config-subif)#
Router(config-subif)#enc
Router(config-subif)#encapsulation dot
Router(config-subif)#encapsulation dot1Q 20
Router(config-subif)#
Router(config-subif)#interface g0/2.30
Router(config-subif)#
%LINK-3-UPDOWN: Interface GigabitEthernet0/2.30, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2.30, changed state to up

Router(config-subif)#encapsulation dot1Q 30
Router(config-subif)#
Router(config-subif)#ip add
Router(config-subif)#ip address 172.16.2.80 255.255.255.252
Bad mask /30 for address 172.16.2.80
Router(config-subif)#ip address 172.16.2.81 255.255.255.252
Router(config-subif)#
```
# Router1
```bash
Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
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
Router(config-if)#ip add
Router(config-if)#ip address 172.16.2.78 255.255.255.255
Bad mask /32 for address 172.16.2.78
Router(config-if)#ip address 172.16.2.78 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#ip address 172.16.2.73 255.255.255.252
Router(config-if)#
Router(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

```
# Router2
```bash
Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#
Router(config)#inter
Router(config)#interface g0/0
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 172.16.2.66 255.255.255.252
Router(config-if)#
Router(config-if)#interface g0/1
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#ip address 172.16.2.69 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#

Router con0 is now available

Press RETURN to get started.

Router>
Router>
Router>en
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#ip route 172.16.0.0 255.255.0.0 172.16.2.70
Router(config)#do show ip inter bri
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     172.16.2.66     YES manual up                    up 
GigabitEthernet0/1     172.16.2.69     YES manual up                    up 
GigabitEthernet0/2     unassigned      YES unset  administratively down down 
Vlan1                  unassigned      YES unset  administratively down down
Router(config)#ip route 172.16.0.0 255.255.0.0 172.16.2.65
Router(config)#
Router(config)#do show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     172.16.0.0/16 is variably subnetted, 5 subnets, 3 masks
S       172.16.0.0/16 [1/0] via 172.16.2.70
                      [1/0] via 172.16.2.65
C       172.16.2.64/30 is directly connected, GigabitEthernet0/0
L       172.16.2.66/32 is directly connected, GigabitEthernet0/0
C       172.16.2.68/30 is directly connected, GigabitEthernet0/1
L       172.16.2.69/32 is directly connected, GigabitEthernet0/1

Router(config)#

```
# Router3
```bash
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#
Router(config)#inter
Router(config)#interface g0/1
Router(config-if)#
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#ip add 
Router(config-if)#ip add
Router(config-if)#ip address 172.16.2.74 255.255.255.252
Router(config-if)#
Router(config-if)#interface g0/0
Router(config-if)#
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

Router(config-if)#
Router(config-if)#
Router(config-if)#ip add
Router(config-if)#ip address 172.16.2.74 255.255.255.252
% 172.16.2.72 overlaps with GigabitEthernet0/1
Router(config-if)#ip address 172.16.2.70 255.255.255.252
Router(config-if)#
Router(config-if)#
Router(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up



Router>
Router>en
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#inter
Router(config)#interface g0/2
Router(config-if)#no shut

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

Router(config-if)#interface g0/2.100
Router(config-subif)#
%LINK-3-UPDOWN: Interface GigabitEthernet0/2.100, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2.100, changed state to up

Router(config-subif)#enca
Router(config-subif)#encapsulation dot
Router(config-subif)#encapsulation dot1Q 100
Router(config-subif)#ip add
Router(config-subif)#ip address 172.16.1.254 255.255.255.128
Router(config-subif)#
Router(config-subif)#interface g0/2.110
Router(config-subif)#
%LINK-3-UPDOWN: Interface GigabitEthernet0/2.110, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2.110, changed state to up

Router(config-subif)#ip address 172.16.2.62 255.255.255.192

% Configuring IP routing on a LAN subinterface is only allowed if that
subinterface is already configured as part of an IEEE 802.10, IEEE 802.1Q,
or ISL vLAN.

Router(config-subif)#ence
Router(config-subif)#enc
Router(config-subif)#encapsulation do
Router(config-subif)#encapsulation dot1Q 110
Router(config-subif)#ip address 172.16.2.62 255.255.255.192
Router(config-subif)#end
Router#
%SYS-5-CONFIG_I: Configured from console by console

Router#show ip inter br
Interface              IP-Address      OK? Method Status                Protocol 
GigabitEthernet0/0     172.16.2.70     YES manual up                    up 
GigabitEthernet0/1     172.16.2.74     YES manual up                    up 
GigabitEthernet0/2     unassigned      YES unset  up                    up 
GigabitEthernet0/2.100 172.16.1.254    YES manual up                    up 
GigabitEthernet0/2.110 172.16.2.62     YES manual up                    up 
Vlan1                  unassigned      YES unset  administratively down down
Router#%IP-4-DUPADDR: Duplicate address 172.16.2.62 on GigabitEthernet0/2.110, sourced by 0001.63D0.11E7

Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#ip route 172.16.0.0 255.255.0.0 172.16.2.69
Router(config)#do show ip route
Codes: L - local, C - connected, S - static, R - RIP, M - mobile, B - BGP
       D - EIGRP, EX - EIGRP external, O - OSPF, IA - OSPF inter area
       N1 - OSPF NSSA external type 1, N2 - OSPF NSSA external type 2
       E1 - OSPF external type 1, E2 - OSPF external type 2, E - EGP
       i - IS-IS, L1 - IS-IS level-1, L2 - IS-IS level-2, ia - IS-IS inter area
       * - candidate default, U - per-user static route, o - ODR
       P - periodic downloaded static route

Gateway of last resort is not set

     172.16.0.0/16 is variably subnetted, 9 subnets, 5 masks
S       172.16.0.0/16 [1/0] via 172.16.2.69
C       172.16.1.128/25 is directly connected, GigabitEthernet0/2.100
L       172.16.1.254/32 is directly connected, GigabitEthernet0/2.100
C       172.16.2.0/26 is directly connected, GigabitEthernet0/2.110
L       172.16.2.62/32 is directly connected, GigabitEthernet0/2.110
C       172.16.2.68/30 is directly connected, GigabitEthernet0/0
L       172.16.2.70/32 is directly connected, GigabitEthernet0/0
C       172.16.2.72/30 is directly connected, GigabitEthernet0/1
L       172.16.2.74/32 is directly connected, GigabitEthernet0/1

Router(config)#
```
# Switch2
```bash
Switch>
Switch>
Switch>en
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#
Switch(config)#inter
Switch(config)#interface ra
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/2 (1), with Switch GigabitEtherne
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/2
Switch(config-if)#sw
Switch(config-if)#switchport mode trunk
Switch(config-if)#sw
Switch(config-if)#switchport trunk
Switch(config-if)#switchport trunk native vlan 999
Switch(config-if)#sw
Switch(config-if)#switchport trunk allow
Switch(config-if)#switchport trunk allowed vlan
Switch(config-if)#switchport trunk allowed vlan 100,110
Switch(config-if)#
Switch(config-if)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface range f0/1-2
Switch(config-if-range)#sw
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#sw
Switch(config-if-range)#switchport access
Switch(config-if-range)#switchport access vlan 100
% Access VLAN does not exist. Creating vlan 100
Switch(config-if-range)#interface range f0/3-4
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 110
% Access VLAN does not exist. Creating vlan 110
Switch(config-if-range)#
Switch(config-if-range)#
Switch(config-if-range)#do show interfaces pro
Switch(config-if-range)#do show interfaces pro
show interfaces pro
                 ^
% Invalid input detected at '^' marker.
	
Switch(config-if-range)#end
Switch#
%SYS-5-CONFIG_I: Configured from console by console

Switch#
Switch#show ip inter
Switch#show inter
Switch#show interfaces ?
  Ethernet         IEEE 802.3
  FastEthernet     FastEthernet IEEE 802.3
  GigabitEthernet  GigabitEthernet IEEE 802.3z
  Port-channel     Ethernet channel port interface
  Vlan             Catalyst Vlans
  etherchannel     Show interface etherchannel information
  status           interface line status
  switchport       Show interface switchport information
  trunk            Show interface trunk information
  |                Output Modifiers
  <cr>
Switch#show interfaces trunk
Port        Mode         Encapsulation  Status        Native vlan
Gig0/2      on           802.1q         trunking      999

Port        Vlans allowed on trunk
Gig0/2      100,110

Port        Vlans allowed and active in management domain
Gig0/2      100,110

Port        Vlans in spanning tree forwarding state and not pruned
Gig0/2      100,110

Switch#
```
# Switch3
```bash
Switch>
Switch>
Switch>en
Switch#
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#
Switch(config)#inter
Switch(config)#interface range f0/1-2
Switch(config-if-range)#sw
Switch(config-if-range)#switchport mode acc
Switch(config-if-range)#switchport mode access 
Switch(config-if-range)#sw
Switch(config-if-range)#switchport access vlan 100
% Access VLAN does not exist. Creating vlan 100
Switch(config-if-range)#interface range f0/3-4
Switch(config-if-range)#switchport mode access 
Switch(config-if-range)#switchport access vlan 110
% Access VLAN does not exist. Creating vlan 110
Switch(config-if-range)#
Switch(config-if-range)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/2
Switch(config-if)#sw
Switch(config-if)#switchport mode trunk

Switch(config-if)#
%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

Switch(config-if)#sw
Switch(config-if)#switchport trun
Switch(config-if)#switchport trunk allowed vlan 100,110
Switch(config-if)#sw
Switch(config-if)#switchport trunk nat
Switch(config-if)#switchport trunk native vlan 999
Switch(config-if)#
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/2 (999), with Switch GigabitEthernet0/2 (1).

Switch(config-if)#
%CDP-4-NATIVE_VLAN_MISMATCH: Native VLAN mismatch discovered on GigabitEthernet0/2 (999), with Switch GigabitEthernet0/2 (1).

Switch(config-if)#
Switch(config-if)#exit
Switch(config)#
Switch(config)#inter
Switch(config)#interface g0/1
Switch(config-if)#sw
Switch(config-if)#switchport mode trunk
Switch(config-if)#sw
Switch(config-if)#switchport trunk allowed vlan 100,110
Switch(config-if)#sw
Switch(config-if)#switchport trunk native vlan 999
Switch(config-if)#
Switch(config-if)#

```

