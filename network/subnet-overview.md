# Subnet Overview 

## 1. Externes LAN (physisches Netzwerk)
- **Subnetz:** 192.168.178.0/24
- **Gateway:** 192.168.178.1 (Router)
- **Zweck:** Internetzugang für Host
- **Belegte IPs:**
  - Host NIC1: 192.168.178.20
  - Router: 192.168.178.1
- **Kommentare:** Externes LAN ist nur für Internet und evtl. externe Tests

## 2. Internes virtuelles Netzwerk (vSwitch)
- **Subnetz:** 192.168.137.0/24
- **Gateway / NAT:** 192.168.137.1 (Server NIC2)
- **Zweck:** Verbindung der VMs untereinander und Zugang zum Internet über NAT
- **Belegte IPs:**
  - Server NIC2: 192.168.137.1
  - Windows11 Client1: 192.168.137.5
  - Windows11 Client2: 192.168.137.6
- **Kommentare:** Alle VMs nutzen Server als primären DNS / Domain Controller

## 3. IPv6 (nicht genutzt)

- **Clients:** eigene IPv6-Adressen innerhalb des Subnetzes

## 4. Übersicht
| Subnetz          | Zweck               | Gateway        | Bemerkung                 |
|------------------|---------------------|----------------|----------------------------|
| 192.168.178.0/24 | Externes LAN / Internet | 192.168.178.1 | Host + Router           |
| 192.168.137.0/24 | Internes vSwitch      | 192.168.137.1 | VMs + NAT über Server NIC2 |
