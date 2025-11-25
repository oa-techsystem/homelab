# Virtual Switch Configuration – Homelab

## 1. Externer vSwitch
| Switch Name      | Typ    | Zugewiesene NIC | Zweck              |
|------------------|--------|-----------------|--------------------|
| External vSwitch | Extern | Host WLAN / LAN | Zugriff der VMs auf das Internet |

## 2. Interner vSwitch
| Switch Name      | Typ     | Zugewiesene NIC | Zweck               |
|------------------|---------|-----------------|---------------------|
| Internal vSwitch | Intern  | -               | Internes Lab-Netz für AD / Clients |

## 3. NAT / ICS
- ICS aktiviert auf Server vNIC2 (Internal)  
- Gateway für internes Subnetz: 192.168.137.1  
- DNS-Server für Clients: Server vNIC2  
- Internet funktioniert über NAT vom Server

