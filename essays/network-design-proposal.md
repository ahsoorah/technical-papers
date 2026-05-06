# Network Design Proposal: H&M Boutique Law Firm
Suriyah Saravanan
ISM 4220: Business Data Communications
Professor Hur
April 30, 2026

---
## Overview
The following proposal outlines a comprehensive network infrastructure design for H&M
Boutique Law Firm, a startup legal practice based in downtown Los Angeles. Founded by
Ronald Harrison and Jeff Mitchell, the firm specializes in corporate tax laws and caters to up-
and-coming small businesses. As a boutique firm handling sensitive client data, H&M requires a
network that is not only high performing but also emphasizes the core tenets of the CIA Triad:
Confidentiality, Integrity, and Availability.

The primary objective of this design is to create a seamless, professional environment
where attorneys and staff can access critical information securely while providing guests with
essential internet services without compromising the firm’s sensitive internal assets. To achieve
this, the design utilizes a Star Topology, providing a centralized point of management that
ensures the infrastructure remains easily scalable as the firm expands its workforce. This plan
focuses on a centralized network architecture that consolidates data storage and authentication
servers, improving security, identity management, and backup efficiency.

The key design highlights of this proposal include:

Logical Network Segmentation: Utilizing virtual local area networks (VLANs) to
isolate guest wireless traffic from the private legal database.

Enterprise-Grade Security: Implementing a hardware-based firewall and strict access
control policies, leveraging centralized authentication, to ensure only authorized
personnel can access sensitive tax records.

Redundancy and Fault Tolerance: Integrating RAID-enabled storage and
uninterruptable power supplies to ensure that technical failures do not result in business
downtime or data loss.

Fiscal responsibility: Selecting a strategic mix of high-reliability hardware and
enterprise gear to keep the total capital expenditure under the $10,000 budget.

This report will detail the technical specifications, physical layout, and IPv4 logical
addressing scheme required to transition the H&M Boutique Law Firm from a concept into a
fully operational, technologically enhanced legal practice.

---
## Business and Technical Requirements
To ensure the success of H&M Boutique Law Firm, the network must be designed to
align with its operational goals and the legal industry’s high standard for data privacy. This
section outlines the specific requirements identified during the initial needs assessment. The
primary business objectives focus on professional efficiency, client satisfaction, and cost-
effective scalability:

Client Amenities: The firm requires a guest wireless network in its waiting room. This is
a business necessity for high-profile clients but must be strictly isolated to prevent any
visibility into legal documents.

Identity Management and Access Control: Because the firm handles sensitive tax data,
Ronald and Jeff require a strict logon policy. Only authorized employees may access firm
computers, ensuring that internal resources remain protected even if a guest is physically
present in the office.

Operational Connectivity: Ronald and Jeff require dedicated desktop stations for
complex tax law research. The receptionist needs a reliable station for client
management, while the paralegal requires a high-performance laptop to maintain
productivity while moving between the conference room and reception area.

Centralized Resource Management: To avoid data silos, all files must be stored on a
secure, centralized server. This ensures that a document started by Ronald can easily be
accessed and reviewed by Jeff or a paralegal.

Business Continuity and Physical Security: The firm views its digital information as its
most critical asset. The business requires “always-on” availability through hardware
redundancy and physical protection. All core networking equipment will be housed in a
locked rack within the designated storage space to prevent unauthorized physical
tampering.

Fiscal Constraints: All identified needs must be met within a strict capital expenditure
budget of $10,000.

The business needs also translate into the following technical specifications:

Physical Topology (Star): The network will utilize a physical Star topology, where all
devices connect to a central managed switch. This ensures that a single cable failure does
not impact the rest of the firm’s operations.

Network Segmentation (VLANs): The network must support IEEE 802.1Q tagging to
create a logical gap between the Guest Wi-Fi (VLAN 20) and the Staff Network (VLAN
10).

Centralized Authentication: To satisfy the “strict logon” requirement, the server will
run a Directory Service (Active Directory or LDAP). This allows for centralized
management of user credentials and the enforcement of the Principle of Least Privilege.

Internet Redundancy (Dual-WAN): To ensure the firm has minimal failure, the router
will support Dual-WAN failover. A primary fiber connection will be backed up by a
secondary LTE/5G connection to maintain uptime.

Storage Redundancy (RAID 1): The central server will utilize a RAID 1 (Mirroring)
configuration. This provides a fault tolerance of

𝑛 − 1

drives, ensuring that if one hard drive fails, the firm may continue to operate without data
loss.

Security Gateway: A hardware-based firewall with Stateful Packet Inspection (SPI) and
an Intrusion Detection & Prevention System (IDPS) will be deployed to monitor and
block malicious traffic at the network edge.

Wireless Standards: Deployment of an 802.11ax (Wi-Fi 6) access point to provide high-
density support for both staff mobility and guest access with modern encryption (WPA3).
Power Protection: Uninterruptable Power Supplies must be installed for the server and
core networking gear to protect against power surges and allow for graceful shutdown
during outages.

---
## Network Design Plan
The network design for H&M Boutique Law Firm is carefully selected to provide a high-
availability environment that balances administrative ease with rigorous security. By utilizing a
centralized management model, the firm can ensure that its digital assets remain protected and
accessible.

As previously suggested, the physical infrastructure will follow a Star topology. In this
configuration, every endpoint, including the lawyer’s workstations, the receptionist’s computer,
the shared printers, and the wireless access point, is connected via dedicated Cat6 cabling to a
central 24-port managed PoE switch.

Rationale for Star Topology: The primary benefit of the star topology for H&M is its
inherent fault isolation. In a high-stakes legal environment, a single cable failure to one
workstation should not inhibit the rest of the firm’s workflow. This layout also simplifies
troubleshooting and allows for seamless scalability; as the firm grows, new devices can
be added to the central switch without reconfiguring the existing network backbone.

Centralized MDF (Main Distribution Frame): All core networking hardware,
including the router, switch, and server, will be housed in the designated Storage Space.
This room will serve as the firm’s secure service room, ensuring that the brain of the
network is physically isolated from public areas like the waiting room.
Security is implemented through a defense-in-depth strategy, protecting the firm’s
sensitive tax data at the network, system, and physical layers.

Logical Segmentation (VLANs): To satisfy the business requirement of providing guest
internet without internal exposure, the network will be partitioned into two distant
VLANs:

Staff VLAN (VLAN 10): Contains the server, all workstations, and printers. This VLAN
has full access to internal resources and the internet.

Guest VLAN (VLAN 20): Dedicated to the waiting room. Traffic on this VLAN is
restricted via firewall rules; users can reach the internet gateway but are prohibited from
communicating with any device on the staff VLAN.

Identity and Access Management (IAM): A centralized Directory Service (Active
Directory) will be deployed on the server. This allows the firm to enforce a strict logon
policy. By utilizing a domain controller, the firm can implement role-based access control
(RBAC), ensuring the paralegal and receptionist only access the specific directories they
need for their tasks, while unauthorized users are blocked at the hardware level.

Edge Security: The hardware-based firewall will be configured with an IDPS and
stateful packet inspection (SPI). This will actively scan incoming traffic for known
exploits and common brute-force patterns, which is critical for a law firm handling
confidential corporate tax records.

To meet the always available business requirement and protect the firm’s critical assets,
the design incorporates multiple layers of fault tolerance:

Storage Redundancy (RAID 1): By utilizing RAID 1 (Mirroring) on the central server,
data is written to two hard drives simultaneously. If one drive suffers a mechanical
failure, the second drive takes over instantly with zero data loss, fulfilling the
requirement that a hardware failure will not stop business operations.

Power Protection: All core infrastructure in the Storage Space will be backed by a UPS.
This protects against Los Angeles power grid fluctuations and provides immediate battery
backup during outages, preventing server crashes and data corruption.

Network Path Redundancy: Utilizing the Dual-WAN capability on the security
gateway, the firm will maintain a primary fiber connection and a secondary failover
connection (5G/LTE). If the primary ISP suffers an outage, the router automatically
switches traffic to the backup to ensure uninterrupted access to the online legal filing
systems.

---
## Devices and Equipment Selection
This section details the specific hardware components selected to implement the H&M
Boutique Law Firm network. The selection criteria focused on enterprise-grade security,
hardware redundancy, and future scalability while strictly adhering to the $10,000 capital
expenditure limit.

The final procurement cost for the infrastructure described below is $9,602.63, providing
a professional-grade environment with a fiscal cushion for tax and implementation
contingencies.

Security Gateway

Ubiquiti Dream Machine SE | 
$518.94

Managed Switch

Ubiquiti USW-24-POE | 
$329.99

Central Server

Dell PowerEdge T150 | 
$2,382.17

Workstations (x3)

Dell OptiPlex 7020 SFF | 
$2,580.00 Total

Mobile Laptop

Lenovo X1 Carbon Gen 13 | 
$1,599.00

Shared Printer

HP LaserJet Pro MFP | 
$639.00

Private Printers (x2)

HP LaserJet M110we | 
$338.00 Total

Power Backup

APC Smart-UPS 1000VA | 
$675.26

Security Rack

NavePoint 6U Enclosure |
$340.27

Cabling

Cat6 Bulk & Connectors |
$200.00

TOTAL: $9,602.63

The core of the network utilizes the Ubiquiti UniFi ecosystem, chosen for its simple
management interface, which allows for sophisticated security without the overhead of a full-
time IT department.

Security Gateway (Ubiquiti Dream Machine SE): This unit serves as the brain of the
network. It was selected for its integrated Stateful Packet Inspection that Intrusion
Detection/Prevention System. By processing traffic at the edge, it ensures that sensitive
corporate tax records are shielded from external threats.

Managed Switching (Ubiquiti USW-24-POE): To support the firm’s growth, a 24-port
switch was selected to provide a high Expansion capacity:

𝐶𝑒

With only 10 ports currently utilized for the server, desktops, and printers, the firm has
significant room for personnel growth:

𝐶𝑒 = 𝑁{𝑡𝑜𝑡𝑎𝑙} − 𝑁{𝑢𝑠𝑒𝑑} = 24 − 10 = 14 ports available

Physical Security (NavePoint 6U Rack): All core infrastructure is housed in a locking
wall-mount enclosure located in the designated Storage Space. This satisfies the non-
functional requirement for physical access control, preventing unauthorized tampering
with the server or gateway.

Server and Data Redundancy (Dell PowerEdge T150, RAID 1): To meet the firm’s
requirement for centralized file storage and a no failure policy, the server hardware is
designed for maximum uptime. The central server is a Dell PowerEdge T150; unlike a
standard consumer PC, the PowerEdge is an enterprise-grade tower designed for 24/7
operation. It will run a Directory Service (Active Directory) to enforce RBAC, ensuring
that only authorized staff can access specific legal folders. The server will be configured
with RAID 1 (Mirroring). By writing data to two physical disks simultaneously, the
probability of total data loss

𝑃𝑓𝑎𝑖𝑙

is drastically reduced. If the probability of a single drive failure is

𝑝

the system failure probability is:

𝑃{𝑓𝑎𝑖𝑙} = 𝑝2

Power Continuity (APC Smart-UPS 1000VA): To protect the server’s integrity, the
UPS provides a battery bridge. This ensures the network stays online during Los Angeles
power flickers and allows the server to perform a graceful shutdown during long outages,
preventing database corruption.

Computing and Printing: The end-user hardware was selected to maximize productivity
for both stationary and mobile staff. The Dell OptiPlex 7020 SFF workstations provide
the lawyers and receptionist with high-speed Intel i5 processors and 16GB of RAM. This
configuration was chosen to handle resource-heavy tax research software and large legal
findings with zero latency. For the paralegal, the Lenovo X1 Carbon Gen 13 provides
premium mobility. Its support for the 802.11ax (Wi-Fi 6) standard ensures a high-speed,
reliable connection that matches the performance of the wired workstations while
roaming between the Conference Room and Reception area.

To satisfy the firm’s requirement for both private and high-volume printing, a tiered
approach was implemented. Two HP LaserJet M110we units provide Ronald and Jeff with local,
private printing for sensitive partner, documents, maintaining confidentiality. Meanwhile, the HP
LaserJet Pro MFP serves as a high-speed, centralized hub for bulk administrative printing and
scanning in the reception area, ensuring that high-volume tasks do not interfere with the partners’
private workflows.

---
## Network Addressing Scheme
To maintain the logical network segmentation requested, the network is divided into two
distinct subnets using a Class C private addressing space. This ensures that Guest traffic on
VLAN 20 is logically separated from the Staff resources on VLAN 10.

Device: Dream Machine (Staff), VLAN: 10, IP Address: 192.168.10.1, Subnet Mask: 255.255.255.0, Default Gateway: N/A

Device: Dream Machine (Guest), VLAN: 20, IP Address: 192.168.20.1, Subnet Mask: 255.255.255.0, Default Gateway: N/A

Device: Central AD Server, VLAN: 10, IP Address: 192.168.10.10, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Ronald's PC, VLAN: 10, IP Address: 192.168.10.21, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Jeff's PC, VLAN: 10, IP Address: 192.168.10.22, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Receptionist PC, VLAN: 10, IP Address: 192.168.10.23, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Paralegal Laptop, VLAN: 10, IP Address: 192.168.10.50, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Main MFP Printer, VLAN: 10, IP Address: 192.168.10.100, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.10.1

Device: Guest Clients, VLAN: 20, IP Address: DHCP Range, Subnet Mask: 255.255.255.0, Default Gateway: 192.168.20.1

The use of a /24 subnet mask (or 255.255.255.0) provides each VLAN with up to 254
unique host addresses. Static IP assignments are utilized for core infrastructure (server, gateway,
printers) to ensure permanent connectivity, while DHCP is utilized for the guest network to
provide plug-and-play access without administrative overhead.

---
## Concerns and Recommendations
While RAID 1 protects against local hardware failure, it does not protect against site-
wide disasters (fire, flood, or theft). It is recommended that the firm implements an encrypted
cloud backup solution (Azure or AWS) to satisfy the integrity and availability parts of the CIA
triad at a secondary location.

Human error remains the leading cause of data breaches. Even with a high-end firewall, a
phishing email can bypass technical controls. I recommend a quarterly security awareness
training program (like KnowBe4) for all staff to maintain a “Human Firewall.” Also, as the client
base grows, the single 802.11ax access point may experience congestion. The current switch
allows for the seamless addition of a second AP in the conference room if wireless latency
becomes an issue.

---
## References
Stouffer, K., Pease, M., Tang, C., Zimmerman, T., Pillitteri, V., Lightman, S., Hahn, A., Saravia, S.,
Sherule, A., & Thompson, M. (2023, September 28). Guide to Operational Technology (OT)
Security. Csrc.nist.gov. https://csrc.nist.gov/pubs/sp/800/82/r3/final

UniFi Cloud Gateways - Ubiquiti. (2024). Ui.com; UI. https://ui.com/cloud-gateways

Cisco. (2023, July 7). IP Addressing and Subnetting for New Users. Cisco.
https://www.cisco.com/c/en/us/support/docs/ip/routing-information-protocol-rip/13788-
3.html

PROVANTAGE: Ubiquiti Networks UDM-SE Dream Machine Special Edition. (2026).
Provantage.com. https://www.provantage.com/ubiquiti-networks-udm-se~7UBNT10F.htm

Micro Center. (2016). Micro Center. https://www.microcenter.com/product/690204/UniFi_USW-24-
POE_Gigabit_Layer_2_Ethernet_Switch

Dell EMC PowerEdge T150 4U Mini-tower Server - 1 x Intel Xeon E-2314 2.80 GHz - 8 GB RAM - 480
GB SSD - Serial ATA, Serial Attached SCSI (SAS) Controller. (2026). Pcnation.com.
https://www.pcnation.com/dell-f11t0-04zz28

NavePoint 6U 600mm Depth Networking Cabinet (Performance Series). (2026). NavePoint.
https://navepoint.com/navepoint-6u-600mm-depth-networking-cabinet-performance-
series/

NIST. (2024). The NIST cybersecurity framework (CSF) 2.0. The NIST Cybersecurity Framework (CSF)
2.0, 2.0(29). https://doi.org/10.6028/nist.cswp.29

American Bar Association. (2019). Rule 1.6: Confidentiality of Information. Americanbar.org.
https://www.americanbar.org/groups/professional_responsibility/publications/model_rules
_of_professional_conduct/rule_1_6_confidentiality_of_information/

Mann, D. (2025, June 2). How you can ensure business continuity during unstable power
conditions. Schneider Electric Blog. https://blog.se.com/datacenter/2025/06/02/how-you-
can-ensure-business-continuity-during-unstable-power-conditions/
