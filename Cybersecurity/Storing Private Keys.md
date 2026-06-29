# Storing Private Keys

## How to secure

###  Miguel
Freshly installed computer
- NO public Wi-Fi
- computer connected via secure WiFi local network isolated from peers
- freshly installed over the internet

Quarantined computer (air-gapped/isolated provisioning environment)
- NO public Wi-Fi
- computer connected via secure WiFi local network isolated from peers or stong-password-protected cellular hotspot
- computer with VPN Kill Switch.
- computer with Firewall turned on (block all unauthorized inbound connections; disable bluetooth, Handoff and Airdrop)
- Secure DNS, DNS-over-HTTPS (DoH) via providers like Cloudflare (1.1.1.1) or NextDNS
- exclusive usage for storing keys (no additional apps, no surfing the internet)

Local Strong Encryption Vaults
- keys in a text file
- open-source trusted tool like VeraCrypt or Cryptomator to encrypt file locally using AES-256 encryption

Shamir's Secret Sharing (SSS)
- cryptographic algorithm splits key into multiple unique, mathematical "shares" (e.g. 3 shares)
- set it up so that any 2 out of the 3 shares are required to rebuild the wallet
- Share 1 in ZK Cloud A, Share 2 in ZK Cloud B, and Share 3 on a physical paper

Zero-Knowledge cloud storage
- SaaS provider located in strong privacy regulatory environment (e.g. Switzerland)
- 20+ character master password


### Two-Factor Cryptographic Separation + Distributed Key Management & Network Sharding
Example:
- Factor 1 (Identity): Your authenticated Google account session.
- Factor 2 (Possession/Knowledge): Your unique 4-digit PIN
- The Ciphertext: Is stored on Phantom's backend infrastructure.
- The Decryption Key: Is broken down into cryptographic "shares" and distributed across an independent, decentralized node network (the Juicebox network).
- The Reconstruction: The only time these pieces come together to form your wallet's private key plaintext is locally on your device, strictly after you successfully complete both the Google sign-in and PIN verification.

### Physical Self-Custody
- paper
- metal

## Vulnerabilities
- Google account breaches
- server-side leaks (cloud leaks, server database breaches)
- rogue employees
- corporate prying
- physical loss
- fire / natural disaster
- physical theft
- social engineering (phishing email scam attacks)
- account lockout
- malware (dormant keylogger, compromised clipboard manager)
- platform risk
- network sniffing
- firmware-level vulnerabilities (e.g. supply-chain attacks on the motherboard or CPU)
- OS installation media compromised
- user forgetfulness / mistakes
- hacker brute-force
