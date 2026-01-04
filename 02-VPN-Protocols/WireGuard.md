# WireGuard Implementation

WireGuard is my primary VPN protocol due to its high performance and state-of-the-art cryptography.

- **Port:** 51820 UDP
- **Encryption:** Curve25519, ChaCha20, Poly1305.
- **Config:** Implemented "Split Tunneling" to access local resources (192.168.1.0/24) while maintaining local internet speed.
- **Performance:** Significant reduction in latency and battery consumption compared to legacy protocols.
