# What is UFW?

**UFW** stands for **Uncomplicated Firewall**. It is like a security guard for the linux system's security door. It decides:

- Who is allowed in.
- Who is blocked.
- Which services can talk to your system.

UFW is just a front-end for powerful linux firewall called **iptables/nftables**.

## What does UFW actually control?

UFW controls:

- **Incomming traffic**
- **Outgoing traffic**
- **Port-based rules**
- **IP based rules**

## How to check whether UFW is installed by default.

On most linux systems UFW comes pre installed. Inorder to check it type:

```bash
sudo ufw status
```

If not installed type:

```bash
sudo apt install ufw
```

## UFW Configuration.

### 1️⃣ What does "UFW Configuration" actually mean.

UFW Configurations is describes as 4 steps:

1. Defining default behaviour.
2. Creating rules.
3. choosing directions.
4. Deciding who, what and how traffic is allowed or denied.

### 2️⃣ Default Policies (Foundation of UFW)

#### 🔐 Default Incoming Policy

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

This will block all the incomming connections except the explicitly allowed connections and allow all the outgoing connections such as browsing, updates, DNS queiries etc...

### 3️⃣ Understanding Traffic Direction

Every firewall rule has a direction:

<table>
  <tr>
    <td><b>Direction</b></td>
    <td><b>Meaning</b></td>
  </tr>
  <tr>
    <td>Incoming</td>
    <td>Traffic coming into your system.</td>
  </tr>
  <tr>
    <td>Outgoing</td>
    <td>Traffic going out</td>
  </tr>
  <tr>
    <td>Routed</td>
    <td>Traffic passing through your system.</td>
  </tr>
</table>

#### Example:

- Someone SSHing into my system -> Incomming
- Your systerm downloading updates -> Outgoing

UFW blocks incoming by default, allows outgoing.

### 4️⃣ Anatomy of a UFW Rule

```bash
sudo ufw allow from 192.168.1.7 to any port 22 proto tcp
```

<table>
  <tr>
    <td><b>Part</b></td>
    <td><b>Meaning</b></td>
  </tr>
  <tr>
    <td>Allow</td>
    <td>Action (allow/deny/reject)</td>
  </tr>
  <tr>
    <td>from</td>
    <td>Source IP address</td>
  </tr>
  <tr>
    <td>to</td>
    <td>Destination</td>
  </tr>
  <tr>
    <td>port 22</td>
    <td>Target port</td>
  </tr>
  <tr>
    <td>proto tcp</td>
    <td>protocol</td>
  </tr>
</table>

### 5️⃣ Actions: allow vs deny vs reject

1. **✅ allow**

   ```bash
   sudo ufw allow 22
   ```

   - Lets traffic pass silently.
  
1. **❌ deny**

   ```bash
   sudo ufw deny 22
   ```

   - Drops traffic.
   - Attacker sees no response.
  
1. **🚫 reject**

   ```bash
   sudo ufw reject 22
   ```

   - Sends a rejection message.
   - Useful for internal networks.
  
### 6️⃣ Ports: The “Doors” of Your System

Ports are how services listen for connections.

<table>
  <tr>
    <td><b>Ports</b></td>
    <td><b>Service</b></td>
  </tr>
  <tr>
    <td>22</td>
    <td>SSH</td>
  </tr>
  <tr>
    <td>80</td>
    <td>HTTP</td>
  </tr>
  <tr>
    <td>443</td>
    <td>HTTPS</td>
  </tr>
  <tr>
    <td>53</td>
    <td>DNS</td>
  </tr>
</table>

**Allow by port number**

```bash
sudo ufw allow 22
```

**Allow port range**

```bash
sudo ufw allow 6000:6007/tcp
```
