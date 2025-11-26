# To-do
- Add RADIUS/TACACS+ support
# Config
```
! Configure enable secret as well as local user accounts
enable secret <PASSWORD>
username superadmin privilege 15 secret 5 <PASSWORD>
username admin secret 5 <PASSWORD> 

! SNMP Settings
snmp-server community public RO  
snmp-server community private RW  
snmp-server location "<ROOM> - <RACK/ROW>"  
snmp-server contact "<FIRST NAME> <LAST NAME> <<EMAIL>>"

! Authentication parameters
aaa new-model  
aaa authentication login default local  
aaa authorization exec default local    

ip domain-name pb218.lab
lldp run

! SSH related settings
ip ssh version 2  
ip scp server enable  

! Configure VLAN 1 with DHCP IP
interface Vlan1  
 ip address dhcp

! Configure Net-MGMT with DHCP IP
vlan 100
 name Net-MGMT

interface Vlan100
 ip address dhcp
```