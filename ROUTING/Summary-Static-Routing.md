# Summary static routing
This is the king of static routing which is used to consolidate multiple static routes into a single broader route 
removing the need to type all the networks to reach a certain destination this is comes when there are alot
of vlans in the same destination
* The topology shown below shows vlans which are in different places but share common given IP address which is subnetted in small networks
now insteady of writing route for each network only we use the common network given to address other networks in for each vlan see the diagram
below
<img width="1505" height="600" alt="SummaryStaticRouting" src="https://github.com/user-attachments/assets/7077ca73-5f66-465a-974e-efef56c0d006" />
The configuration of this are given in file named config2
