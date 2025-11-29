# Homelab Windows Server & Clients

Dieses Repository dokumentiert mein **Homelab** unter **Hyper-V** auf einem **Windows 11 Host**.  

Ziel ist es, ein kleines, funktionsfähiges Netzwerk mit folgenden Komponenten aufzubauen: **Domain Controller, DNS, DHCP, NAT** und mehrere Clients.  

Der Windows Server wurde zu einem Domain Controller hochgestuft, und zwei Windows Clients wurden erfolgreich in die Domäne eingebunden.


---

## Übersicht der virtuellen Maschinen

| VM Name       | Betriebssystem       | Rolle / Funktion                 |
|---------------|-------------------|----------------------------------|
| WinServ2025   | Windows Server 2025 | Domain Controller, DNS, DHCP, NAT |
| Win11Client1  | Windows 11          | Domänen-Client                    |
| Win11Client2  | Windows 11          | Domänen-Client                    |

---

## Netzwerkübersicht

- **Internes Netzwerk:** `192.168.137.0/24`  
- **Externe Verbindung:** Internetzugang über NAT auf dem Server  
- **Hyper-V Switches:**
  - Extern: Host ↔ Internet  
  - Intern: Server ↔ Clients  

---

## Rollen & Dienste auf dem Server

- **Active Directory Domain Services (AD DS)** – Domänen-Controller  
- **DNS** – Namensauflösung im internen Netzwerk  
- **DHCP** – Zuweisung von IP-Adressen an Clients  
- **NAT / IP-Forwarding** – Internetzugang für Clients  

---

## Funktionstests

- Clients erfolgreich in die Domäne `acme.local` eingebunden  
- DNS-Auflösung getestet (`nslookup acme.local`)  
- Internetzugang über NAT überprüft  
- Interne Kommunikation getestet (`ping 192.168.137.x`)  

---

## Verwendete Tools

- **Hyper-V** – Verwaltung von VMs und virtuellen Switches  
- **PowerShell** – NAT & IP-Forwarding Konfiguration  
- **Netzwerktools:** `ipconfig`, `ping`, `nslookup`  

---

## Zusammenfassung

Dieses Homelab demonstriert eine kleine, voll funktionsfähige Windows-Domäne inklusive Clients und Internetzugang. 
Alle VMs sind dokumentiert und getestet, sodass die Infrastruktur leicht nachvollziehbar und reproduzierbar ist.
