# What is Snort?

Snort is a **network intrusion detection system (IDS) and intrusion prevention system (IPS)**.
> Snort listens to network traffic, analyzes packets and alerts or blocks when it sees something suspicious.

Firewall can only control who can talk. Snort checks what they are saying.

## What snort can do?

Snort can mainly operate in 3 main modes:

### 1️⃣ Sniffer Mode

- Just captures and displays packets.
- No detection, No alerts
- Used to understand raw traffic

Example:

```bash
snort -v
```

### 2️⃣ IDS Mode
