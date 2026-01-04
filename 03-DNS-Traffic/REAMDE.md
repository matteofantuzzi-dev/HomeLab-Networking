# DNS Management & Traffic Routing

## Local DNS Resolution
Instead of relying on IP addresses, I configured a local DNS server to map services to human-readable hostnames:
- `nas.home` -> Storage Server
- `router.home` -> Gateway Interface

## Dynamic DNS (DDNS)
Since my ISP provides a dynamic public IP, I deployed a DDNS client (e.g., DuckDNS) to ensure the VPN endpoint remains reachable regardless of IP changes.

## Network Privacy
- Implemented DNS-level filtering (e.g., Pi-hole) to block telemetry and advertisements across all network devices.
