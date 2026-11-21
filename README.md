# Network Scanner Pro v2.0

Kotlin / Jetpack Compose Android network diagnostics project.

## Build
- Android Studio
- JDK 17
- Android SDK Platform 35
- Gradle Sync, then Build > Make Project
- Physical Android device recommended

## Included
- Existing quick/full/custom IPv4 TCP scanner
- Heuristic device fingerprinting based on open ports
- Port URI routing and copy fallback for unsupported protocols
- Tools screen:
  - Watchdog one-shot reachability/latency check
  - SNMP v2c sysDescr/sysName query (SNMP4J)
  - Gateway + local ARP neighbor snapshot
  - ONVIF WS-Discovery probe + CCTV/RTSP port checks
  - Current Wi-Fi connection details
  - Android-visible DHCP server/gateway/DNS details
  - Android total RX/TX counters
  - Forward and reverse DNS
  - Best-effort TTL ping traceroute
  - Local ARP conflict hint
- Room database foundation for devices/subnets/monitoring/SNMP targets

## Important limitations
This is a phone-side diagnostic app. Android cannot reveal all routed VLANs or network appliance state without authorized management-plane access.
- SNMP v2c read-only sysDescr/sysName is implemented. SNMPv3 auth/privacy, SNMP walks, interface tables and VLAN tables are not implemented yet.
- Topology is gateway + local ARP neighbors, not verified physical switch topology. LLDP/CDP and forwarding tables need SNMP/vendor APIs.
- CCTV module sends ONVIF WS-Discovery and checks common TCP ports. Full ONVIF profiles/media configuration and RTSP playback are not implemented.
- Wi-Fi module shows current connection details. Full channel survey requires runtime permission handling, location services and hardware support.
- DHCP module displays Android-visible DHCP parameters. Lease lists require DHCP server/router management access.
- Bandwidth shows Android device total byte counters. Switch/VLAN bandwidth requires SNMP interface counters.
- Watchdog is a one-shot check; scheduled background monitoring/notifications are not implemented.
- DNS supports forward/reverse resolution; MX/TXT/SRV record query UI is not implemented.
- Traceroute uses Android ping with TTL and is device/OS dependent.
- Inventory and IP conflict are initial/local foundations, not a complete network-wide CMDB or duplicate-IP detector.
- Excel/PDF report generation is not included in this package.
- Port 445 is SMB, not HTTPS. It needs an SMB client; the app provides a copyable smb:// endpoint if no handler exists.

Use active probing only on networks and devices you own or are authorized to assess.
