# v2.0 module status

| Module | Implemented behavior | Not included yet |
|---|---|---|
| Scanner | Existing TCP scan modes | OS fingerprinting |
| Port Manager | URI intent routing / copy fallback | Built-in SSH/SMB/RDP clients |
| Device Fingerprint | Port heuristics | Full vendor/model probes |
| Watchdog | One-shot reachability | Scheduled monitoring + notifications |
| SNMP | v2c sysDescr/sysName GET | v3, walks, interface/VLAN tables |
| Topology | Gateway + local ARP snapshot | Verified LLDP/CDP topology |
| CCTV | ONVIF discovery probe + port checks | ONVIF media setup / stream player |
| Wi-Fi | Current connection metrics | Full channel survey/runtime permissions |
| DHCP | Client-visible DHCP values | Lease table |
| Bandwidth | Device RX/TX counters | SNMP interface rate graphs |
| DNS | Forward/reverse lookup | MX/TXT/SRV query UI |
| Traceroute | Best-effort TTL ping | Raw ICMP traceroute |
| IP conflict | Local ARP hint | Network-wide active conflict detection |
| Inventory | Room foundation | Editable UI + export |
| Reports | — | CSV/XLSX/PDF export |
