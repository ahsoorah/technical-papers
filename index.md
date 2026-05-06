# Technical Research & Analysis Papers
**Suriyah Saravanan**<br>*BBA in Management Information Systems, Cybersecurity | Florida Atlantic University*

Welcome to my FAU research paper library. This site hosts whitepapers and deep-dives into systems architecture, cybersecurity concepts, and the future of technology.

---

## Featured Papers

### [Evolution of Network Perimeter Defense: A Comprehensive Analysis of Firewalls and VPNs](./essays/firewall-vpn.md)
*An exploration of the shift from physical boundaries to identity-based security frameworks in the age of AI-driven persistence.*

* **Strategic Scope:** Investigates the transition from stateless packet filtering to Layer 7 Deep Packet Inspection (DPI) and the necessity of **Next-Generation Firewalls (NGFW)**.
* **The Zero Trust Pivot:** Evaluates the integration of **Secure Access Service Edge (SASE)** and ZT-VPNs to neutralize generative AI-enhanced phishing and multi-stage botnet attacks.
* **Real-World Application:** Contextualizes defense-in-depth strategies through the lens of municipal public safety, focusing on the mission-critical availability of fire-rescue IT infrastructure.
* **Future Threats:** Addresses the "Harvest Now, Decrypt Later" mindset of modern threat actors and the emerging requirement for **Post-Quantum Cryptography (PQC)** standards.

---

### [The Vulnerabilities of Virtualization: An Analysis of Cloud Security](./essays/cloud-security.md)
*A deep-dive into the security misalignment caused by rapid cloud adoption and the transition from CapEx-heavy hardware to OpEx-driven virtual environments.*

* **Architectural Critique:** Analyzes the **Shared Responsibility Model** and the common pitfalls of migrating from on-premise infrastructure to Infrastructure as a Service (IaaS) and Software as a Service (SaaS).
* **Identity as the New Perimeter:** Examines **Identity and Access Management (IAM)** failures, specifically the critical role of the **Principle of Least Privilege (PoLP)** and Multi-Factor Authentication (MFA) in neutralizing credential theft and privilege escalation.
* **API & Microservice Security:** Breaks down the fundamental "glue" of the cloud—Application Programming Interfaces (APIs)—with a focus on **Broken Object Level Authorization (BOLA)** and the cascading effects of supply chain risks.
* **Human-Centric Vulnerabilities:** Addresses the gap between automated cloud tools and the human element, arguing that "misconfigurations" are often a symptom of organizational oversight rather than technical failure.

---

### [Network Design Proposal: H&M Boutique Law Firm](./essays/network-design-proposal.md)
*A comprehensive infrastructure design for a specialized legal practice, prioritizing high-availability, the CIA Triad, and fiscal optimization.*

* **Architectural Framework:** Implementation of a centralized **Star Topology** and Main Distribution Frame (MDF) to ensure fault isolation and seamless organizational scalability.
* **Network Segmentation:** Utilization of **IEEE 802.1Q VLANs** to logically isolate guest wireless traffic from sensitive corporate tax records.
* **Redundancy & Fault Tolerance:** Integration of **RAID 1 (Mirroring)**, Dual-WAN failover (Fiber/5G), and UPS battery bridges to achieve a "zero-downtime" mission-critical environment.
* **Fiscal Responsibility:** Successfully engineered a full-stack enterprise solution—including security gateways and Active Directory servers—within a **$10,000 capital expenditure budget**.

---

## Tech Stack
This site is generated using **Jekyll** and **GitHub Pages**, tracking all revisions via **Git** to ensure a transparent, version-controlled research history.
