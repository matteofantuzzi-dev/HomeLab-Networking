# Engineering Log & Troubleshooting

A technical diary of obstacles encountered and solved during the infrastructure setup.

## Solved Issues
1. **Asymmetric Routing:** Fixed issues where VPN traffic was dropped due to incorrect gateway returns.
2. **Permission Conflicts:** Resolved Linux UID/GID mismatches affecting SMB write access.

## Essential CLI Toolkit
- `ss -tulpn`: Checking active listeners.
- `tcpdump`: Real-time packet analysis for VPN debugging.
- `dig/nslookup`: Verifying DNS propagation.
