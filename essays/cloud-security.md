# The Vulnerabilities of Virtualization: An Analysis of Cloud Security

Mishael Norgaisse, Enrique, Sura Saravanan, Sofia Gonzalez

Florida Atlantic University

ISM 4320: Introduction to Cybersecurity

---
## Introduction
As global technology architectures advance, the paradigm of data management is shifting
decisively towards a fully digitized, seamless, cloud-based future. Cloud computing has
transitioned from a niche technical innovation to the backbone of modern enterprise operations.
Historically, organizations depended upon on-premise infrastructure, which required significant
capital expenditure (CapEx) for physical servers, specialized cooling, and on-site security
personnel to guard hardware. However, the emergence of Infrastructure as a Service (IaaS) and
Software as a Service (SaaS), pioneered by providers like Amazon Web Services (AWS) in the
mid-2000s, offered a more agile operational expenditure (OpEx) model (Gartner, 2023).

The cloud is commercially enticing due to its unparalleled scalability and cost-efficiency.
Businesses can now store information wirelessly and remotely, completely bypassing the
logistical burdens of physical asset maintenance. This transition has streamlined operations,
enhanced global collaboration, and fostered a new era of “work from anywhere” efficiency.
However, this rapid adoption has created a security misalignment where the speed of deployment
often outpaces the implementation of robust security protocols. While the cloud alleviates
physical hardware concerns, it introduces complex virtual vulnerabilities. This paper explores the
state-of-the-art security technologies and issues with cloud management, specifically focusing on
three critical pillars: Identity and Access Management (IAM) failures, Insecure APIs/Third-Party
Risks, and Cloud Misconfigurations.

---
## Topic Description
To keep a cloud environment secure, one must first understand the list of everyone who has
the keys. Identity and Access Management, or IAM, is an essential cybersecurity framework of
policies, processes, and technologies that ensures the right individuals and devices access the
correct resources at the right times for the right reasons (Microsoft, 2024). In simple terms, it is a
rulebook for how a department or organization can control what users can and can't access when
using the cloud for work, email, or accessing sensitive company information, ensuring secure
access and compliance with standard policies. IAM carries many benefits; for example, it
permits an employee who works from home to be able to access secure company resources
remotely (with the aid of an enterprise VPN). However, this framework can be prone to issues.

One of them is the failure to properly enforce the Principle of Least Privilege (PoLP). PoLP
dictates that users should only be granted the minimum level of access necessary to perform their
job functions. However, in many cloud environments, users are often given excessive
permissions beyond what is actually required. While this may seem harmless at first, it creates
significant risk. If a low-level account is compromised, or a disgruntled employee exploits their
access, sensitive company information can be exfiltrated and exposed, including data the user
should never have been able to access in the first place.
To mitigate this risk, organizations should strictly enforce least privilege access controls
and regularly audit user permissions. Additionally, Multi-Factor Authentication (MFA) can be
implemented to add an extra layer of security, contributing to a company's Defense-in-Depth
policy. MFA requires users to verify their identity using multiple forms of authentication, such as
a password and a one-time passcode, reducing the likelihood that compromised credentials alone
can lead to unauthorized access.

However, even with these prevention methods in place, IAM systems can still have
serious risks if they are not managed properly. One common issue is credential theft, where
hackers steal login information by phishing emails or weak passwords. Once they get access to
an account, they can sometimes move through the system and reach more sensitive data. Another
risk is insider threats, where employees misuse their access. This can happen intentionally such
as stealing data or accidentally by sending information to the wrong person. There is another
risk. Privilege escalation, when a user ends up getting more access than they were supposed to
have because of system errors, poor management permissions, or hacking. These risks show that
just having basic security measures is not always enough, and we should have more intense
security measures to ensure that important information is protected.

Another major issue in cloud security is cloud misconfiguration. This happens when
cloud systems are not set up correctly, leaving data, applications, and services exposed without
the company even realizing it. Even though cloud platforms are designed to be secure, they are
also very flexible. This means users have a lot of control over how everything is set up. Because
of these small mistakes in settings, this can create big security risks. Since cloud systems are
often complex, it's easy for these types of errors to happen, especially when employees are
working quickly or do not have enough training. Misconfiguration is not usually caused by
hackers or outside attacks, but instead by human error inside the organization, which makes it
even more important to prevent.

One of the biggest reasons misconfigurations happen is the overall complexity of cloud
systems. Modern cloud platforms include many different settings, options, and security controls,
and it is not always easy for companies to fully understand how each one works. As a result,
organizations may rush the setup process and configure services without fully understanding
what each option actually does, rather than carefully checking security details. This issue is made
worse when companies do not have enough trained staff who specialize in cloud security,
increasing the likelihood of mistakes during setup or maintenance.

In addition, large organizations often rely on multiple teams working on different parts of
the same cloud environment. When responsibility is spread out, sometimes it can lead to
confusion or communication gaps where no single team has a complete view of the overall
security configuration. This can result in inconsistent settings or important security steps being
overlooked. What begins as a small configuration error can develop into a serious vulnerability
that exposes sensitive data or allows unauthorized users. For this reason, coordination and clear
responsibilities between teams is essential in cloud systems.

To prevent misconfigurations the most obvious step would be to focus on training and
awareness. Many of these issues occur simply because employees do not fully understand how to
properly configure cloud systems. By giving proper training, companies can reduce mistakes and
ensure that staff follow correct security procedures. This includes understanding how to manage
permissions, apply security controls, and configure cloud services safely. In addition, regular
audits and security checks are essential for maintaining a secure cloud system. Configurations
can change over time as new users, services, and data are added. Meaning a configuration that
was once secure may later become risky and pose a vulnerability for the company. Regular
reviews help identify and fix these issues before they turn into serious problems.

While IAM governs user access, and configurations dictate the environment’s structure,
Application Programming Interfaces (APIs) serve as the fundamental glue that allows cloud
services to communicate. In modern cloud-native architectures, applications are often broken
down into microservices that constantly exchange data via APIs. If an API is poorly designed,
such as lacking robust authentication or failing to encrypt data in transit, it becomes a high-value
target for attackers. According to industry research, API-based attacks have become a preferred
method for data exfiltration because they often bypass traditional network firewalls that are
designed to monitor human traffic rather than machine-to-machine communication (Salt
Security, 2023).

A specific growing concern within this pillar is Broken Object Level Authorization
(BOLA). In a BOLA attack, a hacker manipulates a request to an API to access data objects they
are not authorized to see, such as another user’s personal records or financial information.
Because the API may technically “trust” the requester’s identity but fail to check if that identity
has permission for that specific data, massive amounts of information can be exfiltrated without
triggering any security alarms.

Furthermore, much of the commercial attractiveness of the cloud is due to the ability to
integrate third-party tools and plugins. This introduces significant supply chain risk. Even if an
organization’s internal cloud configuration is flawless, a vulnerability in a third-party vendor’s
software can grant an attacker a backdoor into the primary cloud environment. The 2020
SolarWinds breach is an example of how a compromise in a trusted vendor’s software updates
can have a cascading effect across thousands of cloud tenants. To remediate these risks,
organizations must implement API Gateways to monitor traffic for anomalies and perform
rigorous risk assessments (RAs) on vendors before granting any external software access to their
cloud ecosystem.

---
## Critique / Analysis
One of the main challenges in cloud security seems to be understanding who is actually
responsible for different parts of the system. In most cloud environments, security is shared
between the provider and the customer. The provider usually handles the infrastructure, while the
organization is responsible for things like protecting its data, managing user access, and setting
up configurations (Hashizume et al., 2013). However, it appears that many organizations may not
fully understand this division. In some cases, they might assume that moving to the cloud means
the provider is handling most or all of the security. In reality, a number of security issues seem to
happen because customers do not properly configure their systems. For example, data may be
left publicly accessible or users may be given more permissions than necessary. Based on what
I’ve learned in class, security problems are often more about how systems are managed than
about the technology itself. It seems important for organizations to stay actively involved in their
own security by clearly defining responsibilities, using proper access controls, and regularly
reviewing their systems. Otherwise, the shared responsibility model could potentially increase
risk instead of reducing it.

Misconfiguration appears to be one of the more common issues in cloud security. This
can include things like leaving private data open to the public or not properly limiting user
access. Research suggests that many cloud-related breaches are linked to these kinds of mistakes
(Hashizume et al., 2013). Another major concern involves identity-based attacks. Since cloud
systems rely heavily on login credentials and permissions, attackers often try to gain access by
stealing usernames and passwords. If they are able to access a high-level account or even a
low-level account that has unnecessary access to higher systems, they could potentially control
systems, access sensitive data, or disrupt services. This seems to connect closely to the principle
of least privilege, which suggests that users should only have the access they need to perform
their tasks. When this principle is not followed, it may increase the chances of unauthorized
access. Overall, it appears that cloud security for an organization is becoming more focused on
managing identities rather than just protecting networks. Because more users can access systems
from almost anywhere, organizations likely need to rely more on stronger authentication
methods, such as multi-factor authentication, and monitor user activity more closely.

Protecting data in the cloud seems to be one of the most important parts of cloud security,
although it may also be one of the more difficult areas to manage. When organizations store data
in the cloud, they are relying on external systems to help keep that information secure. This can
raise concerns about confidentiality, integrity, and availability, which are key ideas in
cybersecurity (Bryce, 2019). Encryption is often used to protect data, both when it is stored and
when it is being transferred. However, it seems possible that encryption alone may not always be
enough, especially if it is not managed properly. For example, if encryption keys are not stored
securely or are accessed by the wrong users, the data could still be exposed. From my
perspective, this might suggest that simply having security tools in place does not necessarily
guarantee strong protection. It seems likely that the effectiveness of these tools depends on how
consistently and correctly they are used. This issue could also affect customers. If personal data
is exposed, it may lead to problems such as identity theft or financial loss. Because of this, data
protection might not only be a technical responsibility but also something organizations need to
take seriously in terms of trust and accountability.

Another important aspect of cloud security is the way threats continue to evolve over
time. As more organizations move to the cloud, it seems likely that attackers are also focusing
more on cloud-based systems. Research suggests that threats such as ransomware, API attacks,
and automated hacking techniques are becoming more common (Hashizume et al., 2013).
This means that organizations may not be able to rely only on basic or traditional security
measures. Instead, they might need to take a more proactive approach by identifying potential
risks before they turn into actual attacks. From what I’ve learned in class, this connects to the
idea of defense-in-depth, where multiple layers of security are used to protect systems. For
example, combining access controls, encryption, monitoring tools, and response plans could
make it harder for attackers to succeed. It also seems that cloud security requires constant
updates. As new threats appear, organizations may need to adjust their strategies and tools to
keep up. This suggests that security is not something that can be fully completed, but rather
something that must be continuously improved.

Beyond the technical failures of IAM and APIs, a significant critique of modern cloud
security lies in the gap between society and technology, which is the space between complex
security tools and the humans who operate them. As discussed heavily in this course, security is
only as strong as its weakest link, which is frequently the human element. Organizations often
invest millions in cloud infrastructure but fail to invest in a company's security culture that
educates employees on how to act as human firewalls. This has profound practical implications
for privacy and ethics: for example, when a cloud misconfiguration leads to a data breach, the
ethical burden falls on the organization, but the real-world harm (identity theft, financial loss,
etc). is experienced by the individual customer. Furthermore, the global nature of the cloud
creates a very intricate and complex legal environment. If a Florida-based company stores data in
a foreign country’s data center, which jurisdiction’s privacy laws apply? This analysis suggests
that cloud security is no longer just an IT issue; it is a legal and ethical movement that requires
organizations to move beyond mere compliance and towards true data supervision.

---
## Conclusion
The transition to cloud computing represents one of the most significant and important
shifts ever in the history of information technology. While the commercial attractiveness of
scalability and cost-efficiency is undeniable, this research has demonstrated that the cloud is not
a magical patch for all of security. In fact, the shift towards virtualization has merely changed the
nature of the vulnerabilities we face. As explored in this paper, the most pressing threats; IAM
failures, insecure APIs, and misconfigurations, share a common denominator: they are largely
preventable results of human error and organizational oversight.

The practical implications of these findings are clear. For business organizations, the
Shared Responsibility Model must be treated as a living framework, not a static, unchanging
contract. Security must be baked in from the start of the cloud deployment process, rather than
bolted on as an afterthought. For the person, the shift to the cloud necessitates a higher level of
personal digital hygiene, specifically regarding the protection of identities and credentials.
Ultimately, as technology continues to outpace physical hardware, the new perimeter is no longer
a firewall at the edge of a network: it is the users and administrators of the cloud and the integrity
of the code.

Based on everything discussed in this paper, there are many questions that should be asked
about how to think about cloud security. However, the two most important ones should be
considered. First, if human error continues to be the main cause of cloud vulnerabilities despite
advanced automation tools, at what point does a 'misconfiguration' shift from being a basic
technical mistake to organizational negligence that deserves legal action? These problems keep
happening over and over due to human negligence and poor planning. At what point do we stop
and question the people setting up the misconfigurations, rather than the systems themselves?

The second question that can be asked is this: As the traditional workforce boundary evaporates
in favor of a 'work from anywhere' model, how must our societal understanding of 'identity' shift
if a person's digital credentials become the sole protection preventing global data integrity from
total systemic collapse? Because if everyone just needs authentication, not authorization, to
access systems in the cloud, how long before hackers find easy ways to bypass authentication?
They could then gain access to whatever services they want or need. Alongside the practical
implications of cloud security, there are still many questions that need to be considered.

---
## AI Utilization
For our project, we used artificial intelligence in various ways. For one, we used it to expand
our questions about the topics we were researching. For example, in the section on IAM systems,
after researching what an IAM is, I asked my AI model (using Gemini for this example) whether
there were any ongoing problems with IAMs that are overlooked. Based on this prompt, Gemini
provided detailed information about which IAM issues are usually underestimated in companies
and organizations, and what people are doing to mitigate these issues. It also gave me additional
feedback on how IAMs are not just focused on authentication, and it offered other views on how
authorization can also play a part in making IAM systems better. So the AI model not only
answered our questions but also gave me broader lenses on how to look at the issue. Another
way that we used AI in our research project was to format ideas for how to execute the research
paper as a whole.

As we started our project, we had some issues with how to make our ideas and
findings flow. When challenged with this, we asked an AI model (ChatGPT and Gemini) to give
an outline of how our information should be distributed and structured to get the most attention
of the reader and to make it easier for the reader to understand. After putting a specific prompt to
get this result, it gave a set outline that we could use as a basis to start our paper. Granted, we did
not use all of its formatting suggestions, as we adapted to different needs of the paper as we were
writing, but it helped us get the paper on the right footing so that we weren’t discouraged about
how and what to do to make our paper the best that it could possibly be. Also, some information
and sources were found using AI. Gemini, in particular, can search the web for sources that
support our findings. Even though some were inaccurate and we had to verify these sources, it
still helped a lot by finding additional information for our ideas that we did not have before. So
AI was a wonderful tool to have while doing this research project.

---
## References
Hashizume, K., Rosado, D. G., Fernández-Medina, E., & Fernandez, E. B. (2013a). An analysis
of security issues for cloud computing. Journal of Internet Services and Applications,
4(1), 5. Springeropen. https://doi.org/10.1186/1869-0238-4-5
Hashizume, K., Rosado, D. G., Fernández-Medina, E., & Fernandez, E. B. (2013b). An analysis
of security issues for cloud computing. Journal of Internet Services and Applications,
4(1), 5. Springeropen. https://doi.org/10.1186/1869-0238-4-5
How to Prevent API Attacks - Block & Stop API Attacks. (2023). Salt.security.
https://salt.security/use-cases/stop-api-attacks
Market Share Analysis: Infrastructure as a Service, Worldwide, 2023. (2023). Gartner.
https://www.gartner.com/en/documents/5539195
Microsoft. (2024). What is Identity Access Management (IAM)? | Microsoft Security.
Www.microsoft.com.
https://www.microsoft.com/en-us/security/business/security-101/what-is-identity-access-
management-iam
Rose, S. W., Borchert, O., Mitchell, S., & Connelly, S. (2020). Zero Trust Architecture.
Www.nist.gov, 800-207. https://www.nist.gov/publications/zero-trust-architecture
Top Cloud Threats | CSA. (n.d.). Cloudsecurityalliance.org.
https://cloudsecurityalliance.org/research/topics/top-threats
Top Threats 2025 | 8 Real-World Cybersecurity Breaches | CSA. (2025).
Cloudsecurityalliance.org.
https://cloudsecurityalliance.org/artifacts/top-threats-to-cloud-computing-2025
Amazon Web Services. (2025). What is an API? - API Beginner’s Guide - AWS. Amazon Web
Services, Inc. https://aws.amazon.com/what-is/api/
Khan, M. I. (2025). MANAGING THREATS IN CLOUD COMPUTING: A
CYBERSECURITY RISK MITIGATION FRAMEWORK. International Journal of
Advanced Research in Computer Science, 16(5), 37-43.
https://doi.org/10.26483/ijarcs.v16i5.7347
Alexandre, S., Frederico, B., Reis Arsénio, & Reis Manuel J. C. S. (2025). A Container-Native
IAM Framework for Secure Green Mobility: A Case Study with Keycloak and
Kubernetes. Information, 16(9), 802. https://doi.org/10.3390/info16090802
Vaideeswaran, N. (2025, January 8). What is Principle of Least Privilege (POLP)? | CrowdStrike.
Crowdstrike.com.
https://www.crowdstrike.com/en-us/cybersecurity-101/identity-protection/principle-of-lea
st-privilege-polp/
