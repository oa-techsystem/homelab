# Windows Server 2025 – Setup & Konfiguration

## 1. Systemübersicht
- **Hostname:** `WinServ2025`
- **Rolle:** Domain Controller, DNS, DHCP, NAT
- **Betriebssystem:** Windows Server 2025
- **Domäne:** `acme.local`
- **Status:** Vollständig eingerichtet
- **Virtualisierung:** Hyper-V VM

### Hardware (VM-Konfiguration)
| Komponente | Wert |
|-----------|------|
| CPU | 2 vCPUs |
| RAM | 4 GB |
| HDD | 60 GB |
| Netzwerkadapter | 2 × vNIC |

---


## 2. Netzwerkübersicht

### NIC 1 – Internes Homelab-Netz (192.168.137.0/24)
- Hyper-V Adapter für interne Clients (AD/DNS/DHCP)
- IPv4: 192.168.137.1  
- Subnetzmaske: 255.255.255.0  
- Gateway: *kein Gateway*  
- DNS: 127.0.0.1

### NIC 2 – Externes Netzwerk (Internet)
- Verbindung ins Heimnetz (192.168.178.0/24)  
- IPv4: 192.168.178.20  
- Subnetzmaske: 255.255.255.0  
- Gateway: 192.168.178.1  
- DNS: 127.0.0.1 + IPv6  

---

## 3. NAT-Konfiguration
- Interne Schnittstelle: NIC 1 → 192.168.137.1  
- Externe Schnittstelle: NIC 2 → 192.168.178.20  
- NAT-Ressource: ServerNAT  
- Funktion: Clients erhalten Internet über den Server

---

## 4. Funktionstests
| Test | Ergebnis |
|------|----------|
| Ping auf localhost | ✓ |
| Ping auf 192.168.137.1 | ✓ |
| Ping auf acme.local | ✓ |
| Ping auf 8.8.8.8 | ✓ |
| Client-Internetzugang | ✓ |

---

## 📝 Zusammenfassung
Hauptserver des Homelabs  
Er stellt **AD, DNS, DHCP und NAT** für alle Clients bereit und kommuniziert fehlerfrei im internen und externen Netzwerk.

