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

### 2️⃣ IDS Mode (Detection Mode)

- Monitors Traffic.
- Matches packets against rules.
- Generates alerts when rules match.

Example:

```bash
snort -c /etc/snort/snort.conf -i wlan0
```
### 3️⃣ IPS Mode (Prevention Mode)

- Works inline
- Can drop/block malicious packets.
- Actively stops attacks.

This is dangerous if misconfigured - but powerful.

## How Snort Works

Here's the internal flow:

1. **Packet Capture**

   - Snort listens to a network interface.
  
1. **Preprocessors**

   - Normalize traffic (TCP reassembly, HTTP decoding)
  
1. **Rule Engine**

   - Compares packet against rules
  
1. **Action**

   - Alert, logs, drop or pass.
  
Simple pipeline:

```bash
Traffic ➡️ Preprocessors ➡️ Rules ➡️ Alert / Block
```

## Understanding snort.conf:

### 1️⃣ Define your network (HOME_NET)

```bash
ipvar HOME_NET any
```

change it to your local network:

Example:

```bash
ipvar HOME_NET 192.168.1.0/24
```
**🧠 Meaning:**
> This is my Network. Protect This.

### 2️⃣ External network (EXTERNAL_NET)

Usually:

```bash
ipvar EXTERNAL_NET !$HOME_NET
```
**🧠 Meaning:**
> Everything that is not my network.


