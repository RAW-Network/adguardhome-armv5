# AdGuardHome for ARMv5

Container image for running [AdGuardHome](https://github.com/AdguardTeam/AdGuardHome) on ARMv5 devices.

Official AdGuardHome images don't support ARMv5, so devices like the **MikroTik hEX** (and other ARMv5-only routers) can't run them. This repo provides a working build.

## Usage

Image is hosted on GitHub Container Registry.

**Registry URL:**
```
https://ghcr.io
```

**Image:**
```
raw-network/adguardhome-armv5:latest
```

After the container starts, open the setup wizard at `http://<container-ip>:3000`.

## Ports

| Port | Protocol | Service |
|------|----------|---------|
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |
| 853 | TCP/UDP | DNS-over-TLS |
| 784 | UDP | DNS-over-QUIC |
| 8853 | UDP | DNS-over-QUIC (alt) |
| 5443 | TCP/UDP | DNSCrypt |
| 3000 | TCP | Setup UI |

## How It Works

- CI checks for new AdGuardHome releases daily
- If a new version is found, it builds an ARMv5 image using the official binary
- The image is pushed to GHCR with both `latest` and version tags

## Credits

AdGuardHome is developed by [AdGuard Team](https://github.com/AdguardTeam/AdGuardHome).
This repo only handles container packaging for ARMv5.

Not affiliated with or endorsed by AdGuard. Provided as-is, without warranty.
- Report issues
- Contribute improvements
