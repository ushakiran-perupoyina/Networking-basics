# Networking-basics

What Is Networking?

Networking is the process of connecting multiple computing devices (e.g. computers, servers, routers, switches, IoT devices) so they can communicate, share resources, and transfer data. This is done using wired (Ethernet) or wireless (Wi-Fi) connections, based on a set of rules called protocols (like TCP/IP).


---

🔄 How Networking Works (Step-by-Step)

Here’s how data travels through a network:

1. Devices get connected

Each device (host) gets a network interface (e.g., Ethernet port or Wi-Fi adapter) and a unique IP address on the network.

2. Data is broken into packets

When a device sends data (e.g., a file or a webpage request), it's split into packets. Each packet contains:

Source & destination IP address

Sequence number (for ordering)

Payload (actual data)


3. Data moves through network layers

Using the OSI model (7 layers), data travels through layers like:

Application (HTTP)

Transport (TCP/UDP)

Network (IP addressing & routing)

Data Link (MAC addressing)

Physical (Ethernet cables or Wi-Fi)


4. Routing the packets

On local networks, devices talk through a switch.

For external networks (e.g., internet), packets are routed through a router to reach the destination IP (like a web server).


5. Data reaches the destination

The destination device reassembles the packets in the correct order and hands them up through its own network stack to the application (e.g., browser or server software).


---

🧰 Devices Used to Build a Network

Here are the core networking devices and what they do:

Device	Purpose

Router	Connects different networks (e.g., LAN to the internet), assigns IPs, does NAT
Switch	Forwards packets within a local network based on MAC addresses
Modem	Converts ISP signal (DSL, fiber, cable) to digital signal for routers
Access Point (AP)	Provides wireless (Wi-Fi) connectivity to wired network via Ethernet
Firewall	Inspects and controls incoming/outgoing traffic for security
Server	Hosts services (web, DNS, file, DHCP, etc.) for clients on the network
Client	Any device that requests data/services (laptop, phone, IoT device)



---

🧱 Example: Building a Simple Network

Let’s say you want to build a small office network:

1. ISP gives you internet via fiber.


2. A modem connects to that fiber line.


3. A router connects to the modem, providing:

IP addresses (via DHCP)

NAT to connect LAN to internet



4. A switch connects to the router’s LAN port and expands to more devices (e.g., PCs, printers).


5. A wireless AP connects to the switch to provide Wi-Fi.


6. All client devices (PCs, printers, mobile) connect via switch (wired) or AP (wireless).



[Internet]
    |
  [Modem]
    |
  [Router] -- (DHCP, NAT)
    |
  [Switch]
  /   |    \
PC  Printer  Access Point
               |
             Wi-Fi Devices


---

🛠️ Common Network Types

Type	Description

LAN	Local Area Network (home, office)
WAN	Wide Area Network (internet, or company HQ <-> branches)
WLAN	Wireless LAN (Wi-Fi)
VPN	Virtual Private Network (secure tunneling over internet)
VLAN	Virtual LAN (logical separation inside switches)



---

🧠 How to Use This Knowledge Practically

Home setup: Use a modem-router combo or separate modem + router, configure Wi-Fi with WPA3, connect devices.

Small office: Add managed switches, use VLANs for separation (e.g., Guest vs Admin), install a firewall (like pfSense).

Large enterprise: Use core/distribution/access switch layers, enterprise-grade firewalls, dynamic routing protocols (OSPF, BGP).



---

🧩 Protocols That Glue It Together

Protocol	Function

IP	Addressing & routing
TCP/UDP	Transport layer (reliable/unreliable)
DHCP	Automatic IP assignment
DNS	Resolves domain to IP
HTTP/HTTPS	Web traffic
FTP/SFTP	File transfer




What Is Networking?

Networking is how computers and devices communicate with each other and share data or resources like the internet, files, printers, or servers. Devices can be connected using cables (wired) or Wi-Fi (wireless).


---

🔄 How Networking Works — Step by Step

1. Each device gets an identity (IP address)

Every device on a network needs a unique IP address (like a phone number).

This is either manually assigned or automatically given by a DHCP server (usually your router).


> Example:

Computer A → 192.168.1.10

Computer B → 192.168.1.20





---

2. Data is split into packets

When you send something (like open a website), your data is broken into small pieces called packets. Each packet contains:

Who it's from (source IP)

Who it's going to (destination IP)

The actual data (payload)



---

3. Packets travel through the network

Packets are sent from one device to another using network cables, switches, routers, or Wi-Fi.

There are two main paths:

Local: If you're talking to another device on the same network, data goes through a switch.

External: If you're connecting to the internet, data goes to your router, which sends it to the internet (via your modem).



---

4. Routers guide the data

The router checks where the data needs to go (using the IP address) and sends it to the next step — either:

Another local device

Or out to the internet (via the modem)


Routers also:

Translate private IPs to public IPs (using NAT)

Block unwanted traffic (using firewall rules)

Assign IPs (with DHCP)



---

5. Data reaches the destination and comes back

On the other side, the receiving device reassembles the packets.

It reads the data and sends back a response, like showing a website or downloading a file.



---

🖥️ Quick Real-World Example

Imagine you open a website on your laptop:

1. Your browser requests https://example.com.


2. Your device asks a DNS server to find the IP of example.com.


3. Once found, your laptop sends packets to that IP.


4. Packets go to your router, then out to the internet.


5. The web server receives them and sends back the website’s data.


6. Your browser puts it all together and shows the site.




---

🧠 Summary Table

Step	What Happens

1	Devices get IP addresses
2	Data is split into packets
3	Packets are sent through switches/routers
4	Routers direct packets based on IPs
5	Data reaches the destination and responds



-------------------------------------


Topics to Explore Further:

1. IP Addressing (IPv4, IPv6) — How devices are uniquely identified


2. Subnetting — How networks are divided


3. Routing — How data finds its way between networks


4. Switching vs Routing — What’s the difference?


5. Wi-Fi vs Ethernet — Performance, interference, security


6. Firewall & NAT — Protecting your network and enabling internet access


7. Building a Home or Office Network — Devices, setup, and best practices


8. OSI Model Explained Simply — 7 layers of how networking actually works

--------------------------------------------------------------------------------------

Example: Home or Small Office Network

Here’s what a typical network setup looks like:

[Internet]
    |
  [Modem]                  ← Connects to your ISP
    |
  [Router]                 ← Distributes internet, gives IPs, firewall, NAT
    |
  [Switch] (optional)      ← Expands wired connections
   /     |     \
[PC]  [Printer] [Access Point]  ← Wi-Fi
                    |
               [Laptop] [Phone] [Smart TV]


---

🧠 Step-by-Step Explanation

1. Modem

Connects to your Internet Service Provider (ISP).

Converts the signal from your ISP (fiber, DSL, cable) into something usable by your network.


2. Router

Connects to the modem.

Assigns IP addresses to all devices using DHCP.

Uses NAT (Network Address Translation) to allow many devices to share one public IP.

Acts as a firewall to protect from outside threats.


3. Switch (optional, for wired networks)

A switch connects multiple wired devices together.

It learns the MAC address of each device and sends data only where it’s needed.

Useful when the router doesn’t have enough ports.


4. Access Point (AP)

A device that creates a Wi-Fi network.

Can be built into the router or separate.

Connects wireless devices like phones, laptops, smart TVs.


5. End Devices (Clients)

Devices like computers, printers, tablets, smart TVs, and IoT devices.

Each gets an IP address from the router.

They use TCP/IP to send and receive data.



---

🔧 What Happens When You Browse a Website

1. Your laptop connects to Wi-Fi via the access point.


2. It asks the router for an IP address (DHCP).


3. You type www.example.com into your browser.


4. Your device asks a DNS server (through the router) to get the IP address.


5. Your laptop sends packets to the web server.


6. Packets go from laptop → router → modem → internet.


7. The web server sends data back the same way.


8. Your browser puts the packets back together and shows the site.




---

✅ Key Benefits of This Setup

Modular: Easily add more devices with switches or more APs.

Secure: Router can block or allow traffic (firewall).

Scalable: Add VLANs or servers if needed.


------------------------------------------------------------------------

 Practice Scenario: Small Office Setup (6 Devices)

🏢 The Situation

You are setting up a small office with the following requirements:

🔧 Devices in the network

2 desktop PCs (wired)

1 network printer (wired)

2 laptops (Wi-Fi)

1 IP phone (wired)

1 router with Wi-Fi (includes DHCP)

1 unmanaged switch (8 ports)

Internet is provided via a modem



---

✅ Goals

All devices can access the internet.

Laptops and desktops can print to the shared printer.

The IP phone needs stable connection and priority over other traffic.

Use private IP addresses in the 192.168.10.0/24 range.

Secure the Wi-Fi with WPA2.

Minimize manual configuration where possible.



---

🧱 Step-by-Step Setup

1. Connect the Network Physically

[Internet]
    ↓
[Modem]
    ↓
[Router (192.168.10.1)]
    ↓
[Switch]
 ├── [Desktop PC 1]
 ├── [Desktop PC 2]
 ├── [Network Printer]
 ├── [IP Phone]
 └── [Router's Wi-Fi] → Laptops

> 🔌 Plug the modem into the WAN port of the router.
Then plug the LAN port of the router into the switch.
All wired devices go into the switch.




---

2. Configure Router

IP address of router (gateway): 192.168.10.1

DHCP range: 192.168.10.100 to 192.168.10.200

Wi-Fi security: Enable WPA2, set a strong password

DNS: Use automatic or set to Google (8.8.8.8) or Cloudflare (1.1.1.1)



---

3. Configure Devices

All devices use DHCP to get IPs automatically.

Printer should be given a reserved IP (e.g., 192.168.10.150) via DHCP reservation (so its IP doesn’t change).

Give the IP phone static IP outside the DHCP range (e.g., 192.168.10.10) to avoid IP conflicts.



---

4. Test Connectivity

Use the ping command from one desktop to check:

ping 192.168.10.1     # Test router
ping 192.168.10.150   # Test printer
ping www.google.com   # Test internet


---

5. Enable Quality of Service (QoS) for IP Phone

Go to the router’s web interface.

Enable QoS.

Set high priority for the IP phone’s IP: 192.168.10.10.



---

✅ Results Checklist

Function	Working?

Internet on desktops	✅
Internet on laptops (Wi-Fi)	✅
Printing from laptops/PCs	✅
IP phone online + stable	✅
Wi-Fi secured (WPA2)	✅



---

🧠 Bonus Challenge: Troubleshooting Scenarios

1. Problem: Laptop can’t print
🔍 Check if it's on the same subnet (192.168.10.X), and ping the printer.


2. Problem: Printer not showing up after a power outage
🔍 Maybe got a new IP → Use static DHCP reservation so it keeps the same one.


3. Problem: IP phone breaks up on calls
🔍 Check QoS settings on router → make sure it has high priority.

-------------------------------------------------------------------------------------


Practice Scenario 2: Office Network with VLANs and Guest Wi-Fi

🏢 The Situation

You're setting up a more advanced small business network. This office has:

🔧 Devices

3 office PCs (wired)

1 printer (wired)

2 VoIP phones (wired)

3 employee laptops (Wi-Fi)

5 guest devices (Wi-Fi only)

1 router with VLAN support + firewall

1 managed switch (VLAN support)

1 wireless access point (AP) with dual SSID support



---

✅ Goals

Office devices (PCs, phones, printer) on VLAN 10 (192.168.10.0/24)

Guests on VLAN 20 (192.168.20.0/24) — cannot access office network

VoIP phones get QoS priority

All can access internet

Printer is shared among office PCs/laptops

Wi-Fi has:

Secure Employee SSID for VLAN 10

Open or isolated Guest SSID for VLAN 20




---

🧱 Network Design

[Internet]
   ↓
[Router - VLANs 10 & 20]
   ↓
[Managed Switch]
 ├── VLAN 10: PCs, Printer, VoIP Phones
 ├── VLAN 20: Guest Wi-Fi
 └── [Wi-Fi Access Point]
       ├── SSID: OfficeNet (VLAN 10)
       └── SSID: GuestNet (VLAN 20)


---

🔧 Configuration Steps

1. Create VLANs on the router and switch:

VLAN 10: Office (192.168.10.1/24)

VLAN 20: Guests (192.168.20.1/24)



2. Configure DHCP:

VLAN 10 → DHCP range 192.168.10.100–199

VLAN 20 → DHCP range 192.168.20.100–199



3. Assign ports on the managed switch to the correct VLAN.

Trunk port → for AP

Access ports → for PCs, phones, printer



4. Configure the Wi-Fi AP:

SSID 1 (OfficeNet) → Tagged for VLAN 10

SSID 2 (GuestNet) → Tagged for VLAN 20 + client isolation



5. Enable QoS for VoIP:

Prioritize VLAN 10 traffic for ports used by IP phones (like UDP 5060/5061)



6. Set firewall rules:

Block VLAN 20 (guests) from accessing VLAN 10

Allow both VLANs access to the internet





---

✅ What Should Work?

Function	Working?

Office devices talk to each other	✅
Guests can access internet only	✅
VoIP phones are prioritized	✅
Printer shared within VLAN 10	✅
Guest devices can’t reach printer	✅



---

🧠 Quick Quiz (Answers Below)

Q1: What does a VLAN do in a network?

Q2: If a guest can access the printer, what likely went wrong?

Q3: Why do VoIP phones need QoS?

Q4: What is a trunk port on a switch?

Q5: Which protocol assigns IP addresses in the network?


---

🧪 Answers

A1: A VLAN (Virtual LAN) logically separates devices into different broadcast domains on the same physical switch/network.

A2: The firewall or VLAN isolation between VLAN 20 and VLAN 10 wasn’t configured properly.

A3: VoIP is sensitive to delays—QoS ensures voice traffic gets priority, reducing lag or choppy audio.

A4: A trunk port carries multiple VLANs over one connection (usually to a router or AP).

A5: DHCP (Dynamic Host Configuration Protocol)


---

Want a scenario that involves:

Remote access VPN

Multiple routers

Firewall configuration

Troubleshooting a broken network?

-------------------------------------------------------------------------

Practice Scenario 3: Troubleshooting a Broken Network

🏢 The Situation

You’re called into a small business where some devices can’t access the internet, while others are fine. The network was working yesterday.


---

🔧 Network Setup

1 Router with built-in DHCP (192.168.1.1)

1 Unmanaged switch

Devices:

2 desktop PCs (wired)

1 network printer (wired)

3 laptops (Wi-Fi)


All use DHCP to get IPs from the router



---

🧩 Symptoms

PC1 (wired): No internet, can't ping router

PC2 (wired): Works fine

Printer: Works

Laptop1 (Wi-Fi): Works

Laptop2 (Wi-Fi): No internet

Laptop3 (Wi-Fi): IP address starts with 169.x.x.x

Printer works fine for all devices



---

✅ Your Goals

1. Identify what’s wrong


2. Fix the issues


3. Explain how to prevent it in the future




---

🔍 Step-by-Step Troubleshooting

🖥 PC1: No Internet, Can’t Ping Router

Check IP address: Run ipconfig (Windows) or ifconfig (Linux/macOS)
→ You find it has no IP address or a 169.254.x.x address.


➡ Conclusion: PC1 is not getting a DHCP address → Check cable/switch port

✔ Fix: Reseat or replace the Ethernet cable, test switch port with another device.


---

📶 Laptop3: Has 169.x.x.x IP (APIPA)

➡ This means DHCP failed — the device gave itself a temporary local IP.

✔ Fix:

Make sure the laptop is connected to the right Wi-Fi SSID.

Reconnect to Wi-Fi and try renewing IP:
ipconfig /release && ipconfig /renew

If still no IP → check router DHCP settings or lease limit.



---

📱 Laptop2: Connected, but no internet

Check if it has a valid IP (192.168.1.x)?

Can it ping the router (192.168.1.1)?

Can it ping 8.8.8.8 or only DNS names fail?


➡ If it can ping IPs but not names → DNS problem
➡ If it can’t ping the router → Gateway issue

✔ Fix:

Set DNS manually (e.g., 8.8.8.8)

Reboot router if it’s not responding



---

🔐 Prevention Tips

Reserve static IPs for critical devices like printers

Monitor DHCP leases and extend the range if needed

Keep router firmware updated

Use a managed switch if growth is expected (better diagnostics)

Separate guest Wi-Fi from internal network to reduce load



---

Would you like:

Another realistic failure scenario?

To simulate a remote office VPN setup?

Or start practicing subnetting and IP planning?
