# 🔧 Lab 01: Basic Switch Setup & Security

**Level:** Level 1 — Introduction to Networks
**Tool:** Cisco Packet Tracer

---

## Objective

Build a small LAN consisting of one switch and one PC.
Apply basic security configurations to the switch and
assign IPs to enable switch management and connectivity.

---

## Steps

1. **Build the topology:** Added a Cisco 2960 switch and one PC
2. **Connect:** PC to switch FastEthernet port using
   Copper Straight-Through cable
3. **Hostname:** Changed default name to `sw-Jood`
4. **Secure Privileged Mode:** Set encrypted password using
   `enable secret`
5. **Secure Console:** Set password on `line console 0`
   and enabled login
6. **Secure Remote Access:** Set password on `line vty 0 15`
   and enabled login
7. **Encrypt passwords:** Enabled `service password-encryption`
   to hide plaintext passwords in the config file
8. **Management IP (SVI):** Assigned `192.168.1.1 255.255.255.0`
   to `interface Vlan 1` and brought it up with `no shutdown`
9. **PC IP:** Assigned a static IP in the same subnet
   (e.g. `192.168.1.10`)
10. **Save config:** Saved running config to NVRAM using
    `copy running-config startup-config`

---

## Verification

Ran `ping 192.168.1.1` from the PC to the switch.

**Result: ✅ Success**

This confirms the PC and switch can communicate on the same
network and that management settings are correctly configured.

---

## Configuration Snippet

```
sw-Jood#show running-config
Building configuration...

Current configuration : 1213 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname sw-Jood
!
enable secret 5 $1$mERr$yQRlRAfIGXJbu03q9DD/H.
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
!
... (Interfaces Fa0/2 - Fa0/24) ...
!
interface Vlan1
 ip address 192.168.1.1 255.255.255.0
!
line con 0
 password 7 0822455D0A1654454359
 login
!
line vty 0 4
 password 7 0822455D0A1654454359
 login
line vty 5 15
 login
!
end
```
