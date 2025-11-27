# DHCP Server – Windows Server 2025

## 1. Übersicht
- **Scope:** 192.168.137.0/24  
- **Leases:** 50–150  
- **Gateway:** 192.168.137.1  
- **DNS:** 192.168.137.1  

## 2. Installation
1. Server-Manager → Rollen und Features hinzufügen  
2. DHCP Server auswählen  
3. Scope einrichten → 192.168.137.0/24  

## 3. Funktionstests
| Test | Ergebnis |
|------|----------|
| Lease an Client vergeben | ✓ |
| Client kann Internet nutzen | ✓ |
| Ping auf Gateway | ✓ |

---

## 📝 Zusammenfassung
DHCP liefert automatisch IP-Adressen an Clients im internen Homelab-Netz (192.168.137.0/24).

