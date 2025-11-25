# Networking Overview – Homelab

## 1. Netzwerke 
| Netzwerk            | Subnetz         | Typ       | Zweck                                     |
|--------------------|----------------|-----------|------------------------------------------|
| Externes LAN        | 192.168.178.0/24 | Physisch | Verbindung zum Router / Internet     |
| Internes vSwitch    | 192.168.137.0/24 | Virtuell | Internes virtuelles Netz für Server + Clients  |

## 2. NAT / Internetzugang
- Server vNIC1: Externes Netzwerk → Internetzugang  
- Server vNIC2: Internes Netzwerk → Clients erhalten Internet über NAT / ICS  
- Alle Clients nutzen Server vNIC2 als DNS und Gateway  

## 3. IP-Plan Referenz
- Siehe `ip-plan.md` für alle IP-Adressen der VMs und Netzwerkkarten

