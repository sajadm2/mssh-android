# mssh — alpha development status

Source implementation only: NOT compiled or device-tested. No APK is included.

Implemented in source:
- Persian RTL Compose UI, profile CRUD and Android Keystore/AES-GCM metadata storage.
- Password-based JSch SSH transport with required SHA256 host-key pinning.
- Protected SSH socket, foreground VpnService, loopback authenticated SOCKS CONNECT bridge.
- Vendored HEV native TUN engine, mapped DNS configuration, TCP tunnel.
- Connection controls, elapsed time and native traffic counters.
- GitHub Actions workflow with Java 17, Gradle 8.9, SDK 35 and NDK 27.2.12479018.

Passwords are entered at connection time, not persisted in profiles. No user credentials
are embedded in the source. Runtime secrets cannot be guaranteed erased from JVM memory.

Not implemented: general UDP forwarding, automatic reconnect, per-app routing,
private-key authentication, npvt import or a kill switch. Normal networking returns
when the VPN service closes. DNS/IPv6 behavior and leak prevention remain unverified.

Before use: compile, inspect build errors, test on a physical device, verify host-key
mismatch rejection, authentication failure, routing, DNS/IPv6 leaks, network loss,
service shutdown and traffic counters. Do not treat this alpha as a security tool.

Upload the CONTENTS of MousaviVPN to the repository root, including .github.
Run Actions -> Build mssh alpha APK. Download the artifact only after a successful build.
