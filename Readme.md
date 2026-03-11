# Day 3 - Networking and HTTP Dissection

**Author:** Aishwarya

---

## What I Did

### Mastering Network Fundamentals
1. TCP/IP & DNS (IP/PORT)
2. Raw HTTP Requests
3. Local server & packet capture
4. Document request lifecycle

---

## What Broke

- Sent an HTTP request with the wrong method or missing headers.
- Tried to access a website but DNS was misconfigured.
- Web server running on the wrong port.

**Example**

- DNS misconfiguration.
- Malformed packets in HTTP dissection.

---

## What I Fixed

- Corrected HTTP request syntax.
- Added required headers (`Host`, `User-Agent`).
- Used correct port and server configuration.
- Fixed DNS settings.
- Verified TCP handshake and packet structure.

---

## What I Learned

### Phase 1 – Network Foundations

- Used commands to know the **IP (Internet Protocol) addresses and routes**.
- Learned how to use the **ping command** to check response speed.
- Used `nslookup domain_name` to check:
  - DNS server used
  - IP address of the domain

---

### Phase 2 – DNS & Request Lifecycle

- `dig google.com`  
  Checks how the internet finds Google's IP address and shows detailed DNS information.

DNS Concepts:
- **A Record** → IPv4 Mapping
- **CNAME** → Alias to another domain
- **TTL** → Lifetime of data before DNS cache expires

Command:
```bash
curl -v https://google.com
