Building configuration...

Current configuration : 4404 bytes

!

! Last configuration change at 20:53:51 UTC Wed Mar 10 1993 by admin

!

version 15.0

no service pad

service timestamps debug datetime msec

service timestamps log datetime msec

service password-encryption

!

hostname fCIAS01

!

boot-start-marker

boot-end-marker

!

enable secret 5 changeme

!

username admin password 7 changeme

no aaa new-model

system mtu routing 1500

!

!

ip domain-name ABCMSP

!

!

crypto pki trustpoint TP-self-signed-2674086272

 enrollment selfsigned

 subject-name cn=IOS-Self-Signed-Certificate-2674086272

 revocation-check none

 rsakeypair TP-self-signed-2674086272

!

!

crypto pki certificate chain TP-self-signed-2674086272

 certificate self-signed 01

  3082022B 30820194 A0030201 02020101 300D0609 2A864886 F70D0101 05050030

  31312F30 2D060355 04031326 494F532D 53656C66 2D536967 6E65642D 43657274

  69666963 6174652D 32363734 30383632 3732301E 170D3933 30333031 30303030

  35395A17 0D323030 31303130 30303030 305A3031 312F302D 06035504 03132649

  4F532D53 656C662D 5369676E 65642D43 65727469 66696361 74652D32 36373430

  38363237 3230819F 300D0609 2A864886 F70D0101 01050003 818D0030 81890281

  8100CBDD 961D4F6B 428002FC 8EF9A531 A82D88DA 058919EC 840925A2 436D1B5C

  607B1104 66D589C8 FB1732BD 01F8E313 883043A7 B64D30B4 C1F6AD71 542366F4

  DE438DEA 98DE07AC 96299899 96683FF5 D0770101 2CCB6226 EE144FD8 048A026A

  E6305CCA 5CCF60C3 EDBC6284 81888310 3E984440 F9D166E7 2273CA9B 5CC5CDF0

  E40D0203 010001A3 53305130 0F060355 1D130101 FF040530 030101FF 301F0603

  551D2304 18301680 14C6F423 D31BE972 5551A0F9 C85A05F6 6AA9E1B3 1F301D06

  03551D0E 04160414 C6F423D3 1BE97255 51A0F9C8 5A05F66A A9E1B31F 300D0609

  2A864886 F70D0101 05050003 818100B7 14E7D5E8 D8DF39A5 9E92DB27 E34BDB69

  EE98F260 F1DAF114 A07E5670 285D5130 40401189 6495F443 3795B57B 0AC3E621

  F69AF34E 8C5ECE27 A1522F22 1B873039 B80A4738 6A108ABF FDCC084A C70EC94B

  0BDC677E EF6C5CC8 B4671F28 78D0E9ED D28B31D2 93B2EF3A E3B47824 29A6363A

  2BABBC00 F338CDE6 D2F1DFD9 410B9E

        quit

!

!

!

!

!

spanning-tree mode pvst

spanning-tree extend system-id

!

vlan internal allocation policy ascending

!

ip ssh version 2

!

!

!

!

!

interface FastEthernet0/1

 switchport trunk allowed vlan 10,20,30,40,50,98,99,110

 switchport trunk pruning vlan 10,20,30,40,50,98,99,110

 switchport mode trunk

!

interface FastEthernet0/2

 shutdown

!

interface FastEthernet0/3

 shutdown

!

interface FastEthernet0/4

 shutdown

!

interface FastEthernet0/5

 shutdown

!

interface FastEthernet0/6

 shutdown

!

interface FastEthernet0/7

 shutdown

!

interface FastEthernet0/8

 shutdown

!

interface FastEthernet0/9

 shutdown

!

interface FastEthernet0/10

 shutdown

!

interface FastEthernet0/11

 shutdown

!

interface FastEthernet0/12

 shutdown

!

interface FastEthernet0/13

 shutdown

!

interface FastEthernet0/14

 shutdown

!

interface FastEthernet0/15

 shutdown

!

interface FastEthernet0/16

 shutdown

!

interface FastEthernet0/17

 shutdown

!

interface FastEthernet0/18

 shutdown

!

interface FastEthernet0/19

 shutdown

!

interface FastEthernet0/20

 shutdown

!

interface FastEthernet0/21

 shutdown

!

interface FastEthernet0/22

 switchport trunk allowed vlan 98,99

 switchport trunk pruning vlan 98,99

 switchport mode trunk

 switchport nonegotiate

 spanning-tree portfast trunk

!

interface FastEthernet0/23

 switchport access vlan 99

 switchport mode access

 switchport port-security mac-address sticky

 switchport port-security mac-address sticky b8cb.29b8.2df1

 switchport port-security

 spanning-tree bpduguard enable

!

interface FastEthernet0/24

 switchport access vlan 99

 switchport mode access

 switchport port-security mac-address sticky

 switchport port-security mac-address sticky b8cb.29b8.2deb

 switchport port-security

 spanning-tree bpduguard enable

!

interface GigabitEthernet0/1

 switchport trunk allowed vlan 10,20,30,40,50,98,99,110

 switchport trunk pruning vlan 10,20,30,40,50,98,99,110

 switchport mode trunk

!

interface GigabitEthernet0/2

 switchport trunk allowed vlan 98,99

 switchport trunk pruning vlan 98,99

 switchport mode trunk

 switchport nonegotiate

 spanning-tree portfast trunk

!

interface Vlan1

 no ip address

!

interface Vlan99

 ip address 172.16.99.12 255.255.255.0

!

ip default-gateway 172.16.99.3

ip http server

ip http secure-server

!

!

line con 0

line vty 0 4

 password 7 changeme

 login local

 transport input ssh

line vty 5 15

 login

!

end
