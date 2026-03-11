# Day 3 - Networking and HTTP Dissection

## As Aishwarya

---

# What I Did?

## Mastering Network Fundamentals
1. TCP/IP & DNS (IP/PORT)
2. Raw HTTP Requests
3. Local server & packet capture
4. Document request lifecycle

---

# What Broke?

- Sent an HTTP request with the wrong method or missing headers
- Tried to access a website but DNS was misconfigured
- Web server running on the wrong port  
- Example: `http://localhost:8080`
- DNS misconfiguration
- Malformed packets in HTTP dissection

---

# What I Fixed?

- Corrected HTTP request syntax
- Added required headers (`Host`, `User-Agent`)
- Used correct port and server configuration
- Fixed DNS settings
- Verified TCP handshake and packet structure

---

# What I Learned

## Phase 1 — Network Foundations

- Using commands to know IP (Internet Protocol) addresses and routes
- Using the `ping` command to check connectivity and response time
- `nslookup domain_name`  
  - Shows DNS server used  
  - Shows IP address of the domain

---

## Phase 2 — DNS & Request Lifecycle

- `dig google.com`  
  Checks how the internet finds Google’s IP address and shows detailed DNS information

### DNS Records

- **A Record** → IPv4 mapping
- **CNAME** → Alias to another domain
- **TTL** → Lifetime of DNS cache before it expires

### Debug Website Connection

```bash
curl -v https://google.com
````

Used to test and debug a website connection while showing detailed network communication steps.

---

## Phase 3 — HTTP Deep Dive

### GET Method

* Data sent in the URL
* Can be cached
* Can be bookmarked
* Limited data length
* Should **not modify server data**

### POST Method

* Data sent in request body
* Not cached by default
* Cannot be bookmarked
* No practical size limit
* **Can modify server data**

---

## Phase 4 — Run Your Own Server

Create a simple server and observe request lifecycle.

```bash
mkdir server-lab
cd server-lab
python3 -m http.server 8000
```

Open browser:

```
http://localhost:8000
```

OR

```
http://0.0.0.0:8000
```

---

## Phase 5 — Packet Observation

### TCP 3-Way Handshake

1. SYN → Client
2. SYN-ACK → Server
3. ACK → Client

---

## Phase 6 — Break & Debug

* **Break:** Temporarily stopping an HTTP request during transmission to inspect or modify it.
* **Debug:** The process of identifying and fixing errors in network communication or HTTP transactions.

---

# Commands Used

```bash
ip a
ip route
ping google.com
nslookup domain-name
dig google.com
curl -v https://google.com
```

---

# HTTP Status Codes

| Code | Meaning      |
| ---- | ------------ |
| 200  | OK           |
| 301  | Redirect     |
| 404  | Not Found    |
| 500  | Server Error |

---

# HTTP Requests with CURL

### GET Request

```bash
curl -X GET https://jsonplaceholder.typicode.com/posts/1
```

### POST Request

```bash
curl -X POST https://jsonplaceholder.typicode.com/posts \
-H "Content-Type: application/json" \
-d '{"title":"Darion","body":"engineering","userId":1}'
```

---

# Server Debugging Commands

### Observe Open Ports

```bash
netstat -tuln
```

### Check Running Processes

```bash
ps aux | grep python
```

### Kill Server Process

```bash
kill [PID]
```

### Check Which Process Uses Port

```bash
lsof -i:8000

