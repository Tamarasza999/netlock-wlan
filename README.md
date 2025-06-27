# Network Hardening & WLAN Security

### Tools Extended
- Packet Tracer: Network simulation and topology validation  
- CLI (Command Line Interface): Manual interaction with operating systems and network devices
- RADIUS Server: AAA authentication server for enterprise WLAN
- NetStumbler: WLAN discovery and auditing  
- Suricata: IDS/IPS detection and alerting for network attacks  
- Squid Proxy: HTTP proxy for access control and traffic filtering  
- Kali Linux: Penetration testing and stress-testing validation   

## Network Infrastructure Hardening

**Security Overview**   
- Role-Based Access Control (RBAC) for HR/Finance departments  
- AAA authentication via RADIUS server  
- WPA2-Enterprise with 802.1X authentication  
- Guest network isolation  

**Implementation Summary**  

Cisco Router AAA Configuration:  
Router Basics:
<pre><code>hostname R1
line console 0
password cisco123
login
transport input ssh</code></pre>
RADIUS Auth:
<pre><code>aaa new-model
radius server RADIUS
address ipv4 192.168.2.253 auth-port 1645
key MySecureKey</code></pre>
Wireless Security:
<pre><code>dot11 ssid Staff
authentication open eap TLS
guest-mode
Guest Network:
vlan 100
name Guest
ip access-group Guest-Policy in</code></pre>

WPA2-Enterprise Setup:  
[<img src="media/image14.png" width="400" alt="WPA2-Enterprise 802.1X Setup"/>](media/image14.png)

Guest Network Isolation:

<img src="media/image11.png" width="400" alt="Guest Network VLAN Configuration"/>

**Tools Used**  

Cisco ISE for Zero Trust Policy:
Supporting Configuration:

<pre><code>cisco
R1(config)#radius server RADIUS  // Points to ISE server
R1(config-radius-server)#address ipv4 192.168.2.253 auth-port 1645/</code></pre>
[<img src="media/image5.png" width="400" alt="Cisco ISE Policy Setup"/>](media/image5.png)

Cisco Packet Tracer Topology:  
[<img src="media/image83.png" width="400" alt="Zero Trust Network Diagram"/>](media/image83.png)  

NetStumbler for WLAN Auditing:
[<img src="media/image12.png" width="400" alt="Wireless Network Discovery"/>](media/image12.png)

---

## Zero Trust Implementation

**Security Overview**  
- Firewall rules to block unauthorized traffic
- Suricata IDS to log and detect threats
- Squid Proxy to restrict web access
- Log reviews to validate traffic control    

**Implementation Summary**  

Device Authentication Logs:  
[<img src="media/image0.png"  width="400" alt="RADIUS Authentication Logs"/>](media/image43.png)  

Suricata IDS Alerts:  
[<img src="media/image1.png" width="400" alt="Suricata SYN Flood Detection"/>](media/image56.png)

Squid Proxy Implementation:
[<img src="media/image22.png" width="400" alt="Suricata SYN Flood Detection"/>](media/image22.png)

---

 ## Notes
- All configurations deployed in a lab environment mimicking enterprise networks  
- Security controls were stress-tested using Kali Linux penetration tools  
- Complies with NIST SP 800-53 security controls 
