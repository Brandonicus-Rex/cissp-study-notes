# Domain 4: Communication and Network Security (13%)

## Secure design principles in network architectures

- **OSI model** (7 layers) vs **TCP/IP model** (4 layers: network access/link, internet, transport, application).

| OSI layer | Protocols / devices |
|-----------|--------------------|
| 7 Application | HTTP, DNS, SMTP, SNMP, FTP |
| 6 Presentation | TLS (often placed here), JPEG, ASCII |
| 5 Session | RPC, NetBIOS, SQL sessions |
| 4 Transport | TCP, UDP |
| 3 Network | IP, ICMP, IPsec, routers |
| 2 Data link | Ethernet, ARP, PPP, switches, bridges |
| 1 Physical | Cables, hubs, repeaters |

- **IP:** IPv4 and IPv6 (128-bit addresses; IPsec built into the standard).
- **Secure protocols:**
  - **IPsec:** AH = integrity and authentication; ESP = confidentiality plus integrity. **Transport** mode protects the payload; **tunnel** mode protects the whole packet.
  - **TLS 1.2/1.3.**
  - **SSH.**
  - **Kerberos.**
  - **SNMPv3.**
  - **DNSSEC.**
  - **S/MIME.**
- **Converged protocols:**
  - **iSCSI:** storage over IP.
  - **FCoE:** Fibre Channel over Ethernet.
  - **VoIP.**
  - **InfiniBand.**
  - **Compute Express Link (CXL).**
- **Transport architecture:** topology, data/control/management planes, cut-through vs store-and-forward switching.
- **Performance metrics:** bandwidth, latency, jitter, throughput, signal-to-noise.
- **Traffic flows:** north-south vs east-west.
- **Physical segmentation:** in-band vs out-of-band management, air-gapped networks.
- **Logical segmentation:** VLANs, VPNs, virtual routing and forwarding, virtual domains.
- **Micro-segmentation:** network overlays, encapsulation, distributed firewalls, routers, IPS, Zero Trust.
- **Edge networks:** ingress/egress, peering.
- **Wireless:**
  - Wi-Fi with **WPA2/WPA3** and **802.1X/EAP**
  - Zigbee
  - satellite
- **Cellular/mobile:** 4G, 5G.
- **Content distribution networks (CDN).**
- **Software-defined networks (SDN):** separate control and data planes. Also **SD-WAN.**
- **Virtual private cloud (VPC).**
- **Monitoring and management:** network observability, traffic shaping, capacity management, fault detection.

> **Exam tip:** IPsec **tunnel mode** (whole packet encrypted, new header) is used for site-to-site VPNs. **Transport mode** (payload only) is used host-to-host.

## Secure network components

- **Operation of infrastructure:** redundant power, warranty, support.
- **Transmission media:**
  - physical security of media
  - signal propagation quality
  - **fiber:** immune to EMI and hardest to tap
  - **twisted pair**
  - **coaxial**
- **Network access control (NAC):** 802.1X, posture checking, pre- and post-admission.
- **Endpoint security:** host-based firewall, EDR, anti-malware, HIPS.

| Firewall type | OSI layer | Notes |
|---------------|-----------|-------|
| **Packet filter (static)** | 3 | Checks headers only; fast, stateless |
| **Stateful inspection** | 3–4 | Tracks connection state |
| **Circuit-level proxy** | 5 | E.g., SOCKS |
| **Application-level proxy** | 7 | Deep inspection; slower |
| **NGFW** | 3–7 | Application awareness, IPS, user identity |
| **WAF** | 7 | Protects web applications |

- **Firewall architectures:**
  - **bastion host**
  - **dual-homed**
  - **screened host**
  - **screened subnet (DMZ):** most secure of these

## Secure communication channels

- **Voice, video and collaboration:** conferencing, Zoom/Teams security, VoIP (SIP and SRTP).
- **Remote access:**
  - **VPN:** IPsec, SSL/TLS VPN.
  - **Remote authentication:** **RADIUS** (UDP, encrypts password only), **TACACS+** (TCP, encrypts entire payload, separates AAA), **Diameter** (RADIUS successor).
  - **Tunneling protocols:** PPTP (insecure), L2TP (usually with IPsec), GRE.
  - **Desktop and screen-scraper/virtual application security.**
  - **Jump boxes / bastion hosts.**
- **Data communications:** backhaul networks, satellite.
- **Third-party connectivity:** telecom providers, hardware support, interconnection security agreements (ISAs).

## Network attacks

| Attack | Description | Defense |
|--------|-------------|---------|
| **SYN flood** | Half-open connections exhaust resources | SYN cookies, rate limiting |
| **Smurf** | ICMP to broadcast with spoofed source | Disable directed broadcasts |
| **Fraggle** | Smurf variant using UDP | Disable directed broadcasts |
| **Teardrop** | Overlapping fragments crash systems | Patching |
| **Ping of death** | Oversized ICMP packets | Patching |
| **ARP poisoning** | Fake ARP replies for on-path attacks | Dynamic ARP inspection |
| **DNS poisoning** | Corrupts DNS cache | DNSSEC |
| **VLAN hopping** | Switch spoofing or double tagging | Disable DTP; change native VLAN |
| **Session hijacking** | Stealing session tokens | Encryption, token regeneration |

> **Exam tip:** **TACACS+** is for device administration (TCP, full-payload encryption). **RADIUS** is for network access (UDP, password-only encryption). **Diameter** is RADIUS's successor.

## Key terms

| Term | Definition |
|------|-----------|
| OSI / TCP/IP model | 7-layer / 4-layer network models |
| IPsec AH / ESP | Integrity and authentication / adds encryption |
| Tunnel / transport mode | Whole packet / payload only |
| iSCSI / FCoE | Storage over IP / Fibre Channel over Ethernet |
| Micro-segmentation | Fine-grained segmentation, often per workload |
| SDN | Separates control and data planes |
| NAC | Checks devices before granting network access |
| Stateful firewall | Tracks connection state |
| Screened subnet | Network between two firewalls for public services |
| RADIUS / TACACS+ / Diameter | Remote AAA protocols |
| Smurf / Fraggle | ICMP / UDP broadcast amplification attacks |
| DNSSEC | Digitally signs DNS records |

## Questions to review

1. At which OSI layer does a router operate?
2. Which IPsec protocol provides confidentiality?
3. Which IPsec mode is used for site-to-site VPNs?
4. Which protocol carries SCSI commands over IP networks?
5. Which transmission medium is most resistant to tapping and EMI?
6. Which firewall type inspects traffic at the application layer but is slowest?
7. Which remote AAA protocol uses TCP and encrypts the entire payload?
8. Which attack sends ICMP echo requests to a broadcast address using the victim's spoofed address?

<details>
<summary>Show answers</summary>

1. **Layer 3 (network).**
2. **ESP** (Encapsulating Security Payload).
3. **Tunnel mode.**
4. **iSCSI.**
5. **Fiber optic** cable.
6. **Application-level proxy firewall.**
7. **TACACS+.**
8. A **Smurf** attack.

</details>
