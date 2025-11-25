# IP-Plan

## 1. Externes Netzwerk / Router
| Gerät       | NIC / Port | IP-Adresse     | Subnetzmaske   | Gateway        | Bemerkung         |
|-------------|------------|----------------|----------------|----------------|-------------------|
| Router      | LAN        | 192.168.178.1  | 255.255.255.0  | -              | Internet Gateway  |
| Host NIC1   | Ethernet   | 192.168.178.27 | 255.255.255.0  | 192.168.178.1  | Verbindung Internet |

## 2. Virtuelles Netzwerk (vSwitch)
| Gerät              | NIC        | IP-Adresse      | Subnetzmaske   | Gateway        | Bemerkung                |
|------------------- |-----------|----------------|----------------|----------------|----------------------------|
| Server NIC1        | vSwitch   | 192.168.178.20 | 255.255.255.0  | 192.168.178.1  | Verbindung Internet        |
| Server NIC2        | vSwitch   | 192.168.137.1  | 255.255.255.0  | -              | NAT / ICS                  |
| Windows11 Client1  | vNIC      | 192.168.137.5  | 255.255.255.0  | 192.168.137.1  | Domain Join                |
| Windows11 Client2  | vNIC      | 192.168.137.6  | 255.255.255.0  | 192.168.137.1  | Domain Join                |

## 3. DNS / AD-Server
| Server             | NIC        | IP-Adresse      | Bemerkung        |
|-------------------|-----------|----------------|-----------------|
| Windows Server     | vNIC1       | 192.168.178.20 | DNS für Clients  |
| Windows Server     | vNIC2       | 192.168.137.1  | NAT / Domain     |

## 4. Bemerkungen
- Alle Clients nutzen den Server als primären DNS  
- Subnetz 192.168.137.0/24 für internes vSwitch  
- Subnetz 192.168.178.0/24 für externes LAN / Internet  





