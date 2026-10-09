# Shumbul

This repository contains configs derived from dashax IPs with settings from a reference Trojan config.

## Source
- **IPs/Ports**: From https://raw.githubusercontent.com/amiire81/dashax/main/configs.txt (6 unique IPs)
- **Settings**: From reference Trojan config provided by user

## Settings Applied (from reference config)
- **Protocol**: Trojan
- **Password**: `humanity`
- **Host**: `www.pleadcourt.org`
- **Path**: `/assignment`
- **SNI**: `www.pleadcourt.org`
- **ALPN**: `http/1.1`
- **Fingerprint**: `unsafe`
- **Cipher Suites**: 13 suites (TLS_AES_256_GCM_SHA384, TLS_CHACHA20_POLY1305_SHA256, TLS_AES_128_GCM_SHA256, TLS_ECDHE_ECDSA_WITH_AES_256_GCM_SHA384, TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384, TLS_ECDHE_ECDSA_WITH_AES_128_GCM_SHA256, TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256, TLS_ECDHE_ECDSA_WITH_CHACHA20_POLY1305_SHA256, TLS_ECDHE_RSA_WITH_CHACHA20_POLY1305_SHA256, TLS_ECDHE_ECDSA_WITH_AES_256_CBC_SHA, TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA, TLS_ECDHE_ECDSA_WITH_AES_128_CBC_SHA256, TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256)
- **Fragment (FinalMask)**: 
```json
{
  "tcp": [
    {
      "type": "fragment",
      "settings": {
        "packets": "tlshello",
        "lengths": ["0", "104", "1"],
        "delays": ["0"],
        "maxSplit": "0"
      }
    },
    {
      "type": "fragment",
      "settings": {
        "packets": "1-1",
        "lengths": ["114", "1"],
        "delays": ["1"],
        "maxSplit": "11"
      }
    }
  ]
}
```

## Files
- `configs.txt` - 6 Trojan URIs (one per unique IP:port from dashax)
- `config.json` - Sing-box configuration with all 6 outbounds

## Usage
Import `configs.txt` or `config.json` into any compatible client (SagerNet, FoXray, v2rayNG, NekoBox, etc.).
