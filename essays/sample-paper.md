# Evolution of Network Perimeter Defense: A Comprehensive Analysis of Firewalls and VPNs

Suriyah Saravanan

Department of Business, Florida Atlantic University

ISM 4323: Management Information Assurance Security

Professor Zsuzsa Pusztai

April 26, 2026

---

## Introduction

In our current digital era, the traditional idea that a network has a fixed, physical boundary is no longer accurate. As organizations move towards work models that combines office and remote locations permanently, as well as use infrastructure that connects to the cloud, the total number of points where an attacker can attempt to gain access has increased significantly. According to the Check Point (2025) Security Report, cyberattacks across the world are 44% more frequent than they were in the recent past. Such an increase is occurring due to the rapid growth of systems outpacing security patches, as well as attackers weaponizing generative artificial intelligence (GenAI). Today, where digital security has become a strict, pressing requirement, two of the core pillars of network defense - firewalls and virtual private networks (VPNs) - are no longer just afterthoughts for safety; they are necessities that protect an organization’s assets and the accuracy of data.

It is only through understanding the distinctions between these two technologies that one can create an effective defense-in-depth framework. The firewall, designed to analyze packets, acts as the defender of the network. It is situated at the network edge and helps monitor and control the traffic flow through the network based on certain set criteria or policies (Check Point, 2025). The role of the firewall is to ensure that any unauthorized access is prevented by inspecting the data packets for their source and destination IP addresses, port numbers, and protocols (GeeksforGeeks, 2025). On the other hand, the Virtual Private Network creates an encrypted tunnel between two entities (Sparklight, 2023).
Their connection, therefore, is complementary. The conventional enterprise architecture model shows that the firewall is often the main line of defense, whereas the VPN acts as a secure tunnel for accessing resources protected by that firewall (Outsource IT Security, 2024). However, classic enterprise security designs have become obsolete as modern attacks now involve multiple stages and use advanced methods such as compromised edge devices and phishing enhanced by AI (Oswal, 2024).

This paper will delve into the history of the firewall and the VPN, research findings about them in 2025 trends, and the growing movement towards the implementation of Zero Trust Virtual Private Networks (ZT-VPNs) and Secure Access Service Edge (SASE). Through the implementation of continuous authentication and high-level encryption, organizations can go from having a vulnerable security posture to one that is highly resilient and robust enough to be able to detect and neutralize the sophisticated, evolving cyberattacks of the present and future.

---

## Background

The development of firewalls and VPNs show the history of moving from open, free connectivity to highly restricted, identity-based access controls (IBAC). Understanding the historical trajectory of these tools is essential to knowing why modern integrated frameworks, such as SASE, have become a necessity.
The firewall started out as a primitive packet filter working at Layer 3 of the OSI model. Early stateless firewalls would evaluate packets individually using static information like IP addresses and port numbers without any knowledge of the overall context of the connection (GeeksforGeeks, 2025). The evolution of cyberthreats led to improved firewalls in the form of stateful packet inspection firewalls, capable of observing the state of the connection. In doing so, they analyzed the TCP three-way handshake consisting of synchronization and acknowledgement packets to confirm the legitimacy of packets belonging to an already established connection (Check Point, 2025). Today, the industry has transitioned to the Next-Generation Firewall (NGFW). Unlike their predecessors, NGFWs perform deep packet inspection (DPI) and operate at Layer 7 of the OSI model. This allows administrators to block specific high-risk applications or behaviors within a connection that might otherwise appear legitimate to a standard packet filter (Palo Alto Networks, 2024).

The origins of the use of the VPN can be traced back to the requirement for ensuring secure communication through the public internet. In 1996, the Point-to-Point Tunneling Protocol (PPTP) was developed by Microsoft and came into being as one of the earliest examples of the development of modern VPN technology by establishing an encrypted connection between the user device and the network (Palo Alto Networks, 2024). Until the early 2000s, Site-to-Site VPNs were predominantly used. However, the shift towards a mobile workforce necessitated the rise of Remote Access VPNs, which utilize protocols like IPsec (Internet Protocol Security) and SSL/TLS (Secure Socket Layer/Transport Layer Security) to create secure tunnels for individual users (Sparklight, 2023). While these protocols improved confidentiality, they also introduced new challenges. For instance, SSL VPNs allow for browser-based access without a dedicated client, but they can be more difficult to manage at scale than traditional IPsec tunnels (Palo Alto Networks, 2024).
However, technical efficiency of this secure tunnel technology relies highly on the VPN protocols utilized in securing and sending data packets. The IPsec protocol is still widely implemented for securing traffic between devices on the Internet, as the protocol ensures authentication and encryption of each packet of information throughout the communication session (Palo Alto Networks, 2024). Alternatively, the OpenVPN protocol allows establishing secure connections between two sites or remote hosts and is characterized by its robust open-source implementation. Recently, WireGuard emerged as an efficient solution for the consumer and corporate worlds; the open-source tunnel technology features modern cryptography and high-speed, low-latency communication better than legacy protocols such as PPTP (Palo Alto Networks, 2024).

Moreover, the physical configuration of such defenses is available in several form factors either as hardware or software solutions. A hardware firewall refers to a standalone physical device located between the local network and the internet, which facilitates the need to be physically configured by highly skilled personnel. However, virtual firewalls are software-based and running within a virtual machine/server; hence, they are easy to scale and configure using cloud-based automation software (Palo Alto Networks, 2024). This dual approach has proven necessary in my personal experience as an IT Intern for a Fire Rescue department. The configuration of hardware firewalls in physical offices such as fire stations ensures that the perimeter is secured, but the necessity for virtual firewalls cannot be ignored to ensure that first responders who are on call or working from home can access sensitive and oftentimes mission-critical applications securely.

---

## Research and Findings

The cybersecurity environment in 2025 can be described as a shift from targeted, one-time attacks to chronic, AI-driven persistence. Research on the current tactics used by threat actors reveals that traditional defenses are being bypassed through three key methods: the weaponization of artificial intelligence, the exploitation of edge devices, and the emergence of the threat of post-quantum cryptography.

A primary finding from recent studies is the prominent role played by Generative AI in increasing the speed of cyberattacks. Research shows that GenAI has increased phishing success rates by 30%, given that malicious emails sent out by a threat actor now cannot be differentiated from official corporate communications (Check Point, 2025). Due to the nature of the AI-on-AI warfare, conventional firewalls cannot rely solely on blacklisted URLs; rather, findings stress the need to integrate Precision AI into the internal network’s security framework to detect abnormal behavior before the actual attack takes place (Oswal, 2024). Precision AI was popularized by Palo Alto Networks to refer to a proprietary, ultra-accurate AI algorithm used exclusively for cybersecurity purposes. The Precision AI package consists of three AI systems: machine learning, deep learning, and Generative AI.

Research further indicates that attacks are increasingly targeting edge devices, including the very VPNs and routers meant to protect the network, to establish gateways into the network. Over 20,000 devices were recently controlled by advanced botnets such as “Raptor Train,” operated by state-sponsored actors (Check Point, 2025). This finding shows a major vulnerability: if an edge device like a VPN gateway is compromised, it becomes an unseen point of entry, allowing attackers to move laterally through the internal network while remaining invisible to perimeter firewalls.

This trend is particularly visible in the healthcare sector, which research shows experienced a 47% increase in cyberattacks over the past year (Check Point, 2025). Healthcare and public safety organizations are viewed as high-value targets by threat actors because their operations are time-sensitive and critical to human life; they simply cannot afford the downtime associated with, for example, a ransomware lockdown. In my current role in Fire Rescue IT, I see a direct parallel to this research. Public safety infrastructure relies on seamless operations with firewalls and VPNs to ensure that first responders have constant, secure access to dispatch and medical data. When these edge devices are exploited, the risk is greater than just data loss: it becomes a threat to crisis management and emergency response, reinforcing the need for the proactive patch management and resilient architecture discussed in current security reports.

More forward-looking research findings involve the rise of Post-Quantum Cryptography (PQC). As attackers wait for the debut of quantum computing, they are investing in a “Harvest Now, Decrypt Later” mindset, stealing encrypted data today to decrypt it once quantum technology becomes feasible. However, a more immediate threat has been noted: attackers are now using PQC algorithms to encrypt their own malicious traffic (Oswal, 2024). Because many current network security products lack the ability to inspect PQC encrypted data, threats can bypass firewalls entirely by hiding inside these advanced encryption tunnels.

Finally, academic research into the Zero Trust VPN framework shows a solution to the latency and security gaps present in traditional VPNs. The ZT-VPN model addresses critical concerns regarding throughput and scalability by continuously verifying every user and device attempting to access resources (Zohaib et al, 2024). Unlike a standard VPN that grants broad network access upon login, the ZT-VPN framework enforces least-privilege access permissions, ensuring that even if a user’s credentials are stolen, the attacker is limited to a single, isolated channel rather than the entire corporate infrastructure.

---

## Conclusion

The evolution of network security from its traditional hardware-oriented and centralized approach into a more decentralized and identity-driven one is a much-needed change amidst an ever-growing hostile environment of digital threats. As shown throughout this paper, the old distinctions between firewalls and VPNs are being blurred by new frameworks such as SASE and ZT-VPN. Although a firewall is still crucial for inspecting packets and a VPN ensures security through encryption, it’s noted that the increase in cyberattacks described by Check Point shows that each is not enough on its own.

The results of this research show that the future of cybersecurity will be defined by the AI vs. AI arms race and the proactive implementation of post-quantum cryptography standards. The discovery that attackers are leveraging GenAI to create realistic phishing campaigns and PQC to conceal their activities means that companies should seek to administer Precision AI and continual authentication (Oswal, 2024). Being an MIS specialist in the sphere of public safety technology, I can confidently state that the implementation of these technologies is not just a technical upgrade but an eventual mission-critical necessity. The Zero Trust framework will become the only logical path forward for industries such as rescue services, where the integrity of information and availability of systems can become a matter of life and death.

Ultimately, the aim of a modern security system should be to create a frictionless user experience without compromising on security. By utilizing the comprehensive protection offered by next-gen firewalls along with the safe and secure access provided by ZT-VPNs, organizations can construct a formidably resilient internal network. This strategy not only helps in detecting and neutralizing the existing threats of today, but futureproofs the system and equips it to handle the emerging quantum and AI-driven threats of tomorrow.

---

## References

Anand Oswal. (2024, December 12). 8 Trends Reshaping Network Security in 2025. Palo Alto Networks Blog. https://www.paloaltonetworks.com/blog/2024/12/8-trends-network-security-in-2025/

Check Point Software’s 2025 Security Report Finds Alarming 44% Increase in Cyber-Attacks Amid Maturing Cyber Threat Ecosystem - Check Point Software. (2025, January 14). Check Point Software. https://www.checkpoint.com/press-releases/check-point-softwares-2025-security-report-finds-alarming-44-increase-in-cyber-attacks-amid-maturing-cyber-threat-ecosystem/

netalit. (2025, February 25). VPN vs. Firewall: 4 Key Differences. Check Point Software. https://www.checkpoint.com/cyber-hub/network-security/what-is-firewall/vpn-vs-firewall-4-key-differences/

Palo Alto Networks. (2024). Types of Firewalls Defined and Explained. Palo Alto Networks. https://www.paloaltonetworks.com/cyberpedia/types-of-firewalls

What is a VPN? - Palo Alto Networks. (2024). Www.paloaltonetworks.com. https://www.paloaltonetworks.com/cyberpedia/what-is-a-vpn

Zohaib, S. M., Sajjad, S. M., Iqbal, Z., Yousaf, M., Haseeb, M., & Muhammad, Z. (2024). Zero Trust VPN (ZT-VPN): A Systematic Literature Review and Cybersecurity Framework for Hybrid and Remote Work. Information, 15(11), 734. https://doi.org/10.3390/info15110734
‌
GeeksforGeeks. (2025, June 22). Firewall vs VPN: Which One to Use in 2025. GeeksforGeeks. https://www.geeksforgeeks.org/ethical-hacking/relationship-between-vpn-and-firewall/

Bright, A. (2024, July 4). Firewalls and VPNs: How They Work Together to Secure Remote Access -. OutsourceITsecurity.com. https://outsourceitsecurity.com/firewalls-and-vpns-how-they-work-together-to-secure-remote-access

What is VPN? Firewall? Both? We’ve Got Answers to Your Questions. (2023). Sparklight Business. https://business.sparklight.com/the-wire/tech-talk/cybersecurity/what-vpn-firewall-both-weve-got-answers-your-questions
