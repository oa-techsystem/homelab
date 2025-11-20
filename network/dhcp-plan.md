# DHCP Plan

## 1. Allgemeine Infos
- DHCP läuft auf: **Windows Server NIC2 (192.168.137.1)**
- Internes Subnetz: 192.168.137.0/24
- Gateway für VMs: 192.168.137.1
- Primärer DNS: 192.168.137.1 (Server DNS)
- Lease-Time: 24 Stunden

## 2. DHCP-Bereiche (Scopes)
| Bereich / Scope        | Start-IP      | End-IP        | Subnetzmaske   | Gateway        | Bemerkung        |
|------------------------|---------------|---------------|----------------|----------------|------------------|
| Internal VM Scope      | 192.168.137.10| 192.168.137.100| 255.255.255.0 | 192.168.137.1  | Für alle interne VMs |

## 3. Reservierungen
| Hostname             | MAC-Adresse        | Reservierte IP | Bemerkung     |
|----------------------|--------------------|----------------|---------------|
| Windows11-Client-1   | 00-15-5D-B2-1B-03  | 192.168.137.5  | Domain Join   |
| Windows11-Client-2   | 00-15-5D-B2-1B-04  | 192.168.137.6  | Domain Join   |

## 4. Optionen / Zusatzkonfiguration
| Option                  | Wert                 | Bemerkung                       |
|-------------------------|----------------------|---------------------------------|
| Router (Default Gateway)| 192.168.137.1        | Clients wissen, wohin Internetpakete gehen |
| DNS-Server              | 192.168.137.1        | Primär, für AD Domain           |
| Lease Duration          | 24h                  | Dauer, wie lange eine IP reserviert bleibt |
