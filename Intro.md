# Intro 

Hello potential viewer! My name is Josh Olsen. The following content is a walkthrough for a home lab that I want to create for some helpdesk/networking experience. Each readme posted is meant to showcase each step I took to complete my home lab, as well as the concepts I learned along the way. The project consists of the following. Thank you. 

# The pieces:

### Proxmox — the host. One physical box that runs everything else as virtual machines.
### pfSense — the firewall/route. Sits between the internet and your lab, routes traffic between the different network segments, and enforces security rules about what can talk to what.
### VLANs (the segments) — instead of one flat network, the lab is split into separate zones, each its own little network:
#### VLAN 10 — Servers (where the domain controller lives)
#### VLAN 20 — Users (where the Windows client lives)
#### VLAN 99 — Management (admin access)
#### VLAN 666 — Attacker (Kali, walled off)
### Domain Controller (DC) — a Windows Server running Active Directory, DNS, and DHCP. The “identity” core — it manages users, logins, and network addresses. (From your first build; gets rebuilt onto VLAN 10.)
### Windows client — a normal Windows 11 machine joined to the domain, like an employee’s PC. Lives on VLAN 20.
