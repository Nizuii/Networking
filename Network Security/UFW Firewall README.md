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
