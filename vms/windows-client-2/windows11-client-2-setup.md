# Windows 11 Client 2 - Setup & Konfiguration

## 1. Systemübersicht
- **Hostname:** `Win11Client2`
- **Rolle:** Domänen-Client
- **Virtualisierung:** Hyper-V VM
- **Domäne:** `acme.local`
- **Status:** Erfolgreich der Domäne beigetreten
- **CPU:** 2 Kerne
- **RAM:** 4 GB
- **Festplatte:** 30 GB (virtuell)

---

## 2. Netzwerk-Konfiguration

### Ethernet – Hyper-V Network Adapter
| Einstellung | Wert |
|------------|------|
| **DHCP** | Nein |
| **IPv4-Adresse** | `192.168.137.6` |
| **Subnetzmaske** | `255.255.255.0` |
| **Gateway** | `192.168.137.1` |
| **DNS-Server** | `192.168.137.1` |
| **MAC-Adresse** | `00-15-5D-B2-1B-04` |
| **DNS-Suffix** | `acme.local` |

---

## 3. Vollständige ipconfig /all (Dokumentation)

### Windows-IP-Konfiguration

| Parameter            | Wert         |
| -------------------- | ------------ |
| Hostname             | Win11Client2 |
| Primäres DNS-Suffix  | acme.local   |
| Knotentyp            | Hybrid       |
| IP-Routing aktiviert | Nein         |
| WINS-Proxy aktiviert | Nein         |
| DNS-Suffixsuchliste  | acme.local   |

### Ethernet-Adapter Ethernet:

| Parameter                          | Wert                              |
| ---------------------------------- | --------------------------------- |
| Beschreibung                       | Microsoft Hyper-V Network Adapter |
| Physische Adresse                  | 00-15-5D-B2-1B-04                 |
| DHCP aktiviert                     | Nein                              |
| Autokonfiguration aktiviert        | Ja                                |
| IPv4-Adresse                       | 192.168.137.6 (Bevorzugt)         |
| Subnetzmaske                       | 255.255.255.0                     |
| Standardgateway                    | 192.168.137.1                     |
| DNS-Server                         | 192.168.137.1                     |
| NetBIOS über TCP/IP                | Aktiviert                         |

---

## 4. Domain Join
| Einstellung | Wert |
|------------|------|
| **Domäne** | `acme.local` |
| **Domain Controller** | `SRV-DC1.acme.local` |
| **Join-Status** | ✓ Erfolgreich |

**Durchgeführt über:**  
`Systemsteuerung → System → Erweiterte Systemeinstellungen → Computername → Domäne beitreten`

---

## 5. Funktionstests
| Test | Ergebnis |
|------|----------|
| `ping acme.local` | ✓ Erfolgreich |
| `ping 192.168.137.1` | ✓ Gateway erreichbar |
| `nslookup acme.local` | ✓ DNS-Auflösung korrekt |
| Anmeldung mit Domänenkonto | ✓ Erfolgreich |

---

## 📝 6. Zusammenfassung
Client 2 ist vollständig eingerichtet, besitzt eine statische IP-Adresse, nutzt den Domain Controller als DNS, ist erfolgreich der Domäne `acme.local` beigetreten und kommuniziert fehlerfrei im Netzwerk `192.168.137.0/24`.

