# DNS Server – Windows Server 2025

## 1. Übersicht
- Primärzone: `acme.local`  
- Reverse Zone: 192.168.137.x  
- Weiterleitungen: Cloudflare (1.1.1.1), Google (8.8.8.8)  

## 2. Installation
1. Server-Manager → Rollen und Features → DNS Server  
2. Primärzone für Domäne `acme.local` anlegen  
3. Reverse Lookup Zone erstellen  

## 3. Funktionstests
| Test | Ergebnis |
|------|----------|
| `nslookup acme.local` | ✓ |
| Client-DNS-Auflösung | ✓ |

---

## 📝 Zusammenfassung
DNS ist korrekt eingerichtet, löst interne Domänen- und externe Adressen auf, unterstützt die Domain Controller Funktionalität.

