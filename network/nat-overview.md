# NAT Overview (Server)

## 1. Zweck
- Interne VMs (192.168.137.0/24) sollen Internetzugang haben.
- NAT / ICS läuft über Windows Server NIC2 (192.168.137.1).

## 2. NAT-Konfiguration
| Parameter                      | Wert                          | Bemerkung                                  |
|--------------------------------|-------------------------------|--------------------------------------------|
| NAT-Gateway                    | 192.168.137.1                 | Server NIC2                                |
| Internes Subnetz               | 192.168.137.0/24              | VMs                                        |
| Externes Netzwerk              | 192.168.178.0/24              | Host + Router                              |
| Firewall                       | Windows-Firewall auf Server   |                                            |
| DNS-Server für VMs             | 192.168.137.1 (Server DNS)    | Primär, für Domain-Auflösung               |
| Optionale öffentliche DNS      | 8.8.8.8                       | Backup, Google DNS                         |

## 3. Funktionsweise
1. Server empfängt Daten von internen Clients über NIC2 (192.168.137.x).  
2. Server leitet die Pakete über NIC1 (192.168.178.x) ins Internet weiter.  
3. Antwortpakete kommen zurück zum Server und werden wieder an die interne VM weitergeleitet.

## 4. Hinweise
- NAT muss **aktiviert** sein (Erfolgte über PowerShell).  
- Interne VMs dürfen nur **Server als Gateway** nutzen.  




