---
created: 2026-08-25 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 11 — cloud computing types, cloud security controls, and virtualization security
mod.: 2026-08-25 20:12:00
aliases:
  - security+ module 11
  - cloud and virtualization security
tags:
  - study/security-plus
  - study/security-plus/module-11
---

# Module 11 - Cloud and Virtualization Security

## Objectives

1. [[#Objective 1 - Introduction to Cloud Computing|List and describe the different types of clouds and their locations, architectures, and models]]
2. [[#Objective 2 - Cloud Computing Security|Describe cloud security controls]]
3. [[#Objective 3 - Virtualization Security|Explain virtualization security]]

---

## Objective 1 - Introduction to Cloud Computing

### What Is Cloud Computing?
- **Cloud computing**: model for enabling convenient, on-demand network access to a shared pool of configurable computing resources (NIST definition)
- Resources can be rapidly provisioned and released with minimal management effort or service provider interaction
- Cloud entities that offer computing are called **cloud service providers**
- **Pay-per-use** computing model: customers pay only for resources they need
- Similar to hosted services but at different scale; supports multiple tenants with rapid automatic scalability and elasticity

#### Cloud Computing Advantages

| Characteristic | Explanation |
|---|---|
| **On-demand self-service** | Consumer can make changes without requiring human interaction from the service provider |
| **Universal client support** | Virtually any networked device can access cloud computing resources |
| **Invisible resource pooling** | Physical and virtual resources pooled together; customer has little knowledge of physical location |
| **Immediate elasticity** | Computing resources can be increased or decreased quickly to meet demands |
| **Metered services** | Fees are based on the computing resources used |

#### Cost Savings Factors
- **Elasticity and scalability**: expand and reduce resources according to specific requirements
- **Pay-per-use**: pay for services when used, short or long term
- **On demand**: services only activated when needed; reduces hardware/software purchases and IT staffing
- **Resiliency**: cloud provider isolates failures and migrates hardware/software without user knowledge

### Types of Clouds

| Cloud Type | Description |
|---|---|
| **Public cloud** | Services and infrastructure offered to all users via the Internet |
| **Community cloud** | Open only to specific organizations with common concerns (e.g., HIPAA-compliant hospitals) |
| **Private cloud** | Created and maintained on a private network; highest security and control but reduced cost savings |
| **Hybrid cloud** | Combination of public and private clouds |

### Cloud Locations

| Location | Description | Example |
|---|---|---|
| **On-premises** | Computing resources located on the organization's campus ("on-prem") | Desktop computer, LAN, data center |
| **Off-premises** | Computing resource hosted and supported by a third party | Remote backup facility |
| **Fog** | Decentralized computing between data source and cloud | Automated guided vehicles on shop floor |
| **Edge** | Computing performed at or near the source of data | IoT device |
| **Cloud** | Remote facility for computing | AI processing engine |

### Cloud Architecture

- **Thin client**: computer that runs from resources stored on a central cloud server instead of a localized hard drive
- **Transit gateway**: technology allowing organizations to connect all VPCs, data centers, remote offices, and gateways into a single managed source (hub-and-spoke topology)
- **Serverless infrastructure**: servers exist but capacity planning, installation, setup, and management are invisible to the user (cloud provider handles them)

### Cloud Models

#### Software as a Service (SaaS)
- **SaaS**: cloud computing hosted software environment
- Eliminates software purchase, installation, maintenance, upgrades, and patches
- Provider centrally manages software on a per-user basis
- Accessed via a web browser; no specialized software installation needed
- Includes provisions for bandwidth and storage

#### Platform as a Service (PaaS)
- **PaaS**: provides a software platform on which the enterprise can build and host their own applications
- Platform used as development framework to build, debug, and deploy apps
- Provides moderate degree of control; cloud provider guarantees elasticity and scalability
- Not all traditional applications migrate seamlessly; best results from cloud-native apps

#### Infrastructure as a Service (IaaS)
- **IaaS**: provides unlimited "raw" computing, storage, and network resources
- Enterprise builds own virtual infrastructure (CPU, memory, storage, networking)
- Enterprise loads own OS (or rents from provider) and software
- Scaling and elasticity are enterprise's responsibility
- Three-tier architecture decision: which tiers to migrate to cloud vs. keep on-prem

#### Anything as a Service (XaaS)
- **XaaS**: broad category of subscription services related to cloud computing
- Any IT function or digital component delivered as a service
- Examples: **Security as a Service (SECaaS)**, Communication as a Service (CaaS), Desktop as a Service (DaaS), Healthcare as a Service (HaaS)

### Cloud Management
- Managing cloud resources can be more challenging than on-prem resources
- May involve multiple providers; proper management is cumbersome

#### Local Management
- **Services integration**: combined management of multiple services into a single entity
- Requires written resource policies: responsible party, duties, allowed/prohibited uses, acquisition processes
- **Shadow IT**: cloud environments set up by employees using their own credit cards (serious threat)

#### Service Providers
- **Managed service provider (MSP)**: delivers network, application, infrastructure, and security services through ongoing support
  - Can manage on customer premises, MSP's data center, third-party data center, or cloud
- **Managed security service provider (MSSP)**: specialized MSP providing cybersecurity monitoring and management
  - Services: antivirus, spam blocking, IDS, firewalls, VPNs, system changes/upgrades

### Cloud-Native Microservices
- **Microservices** (cloud-native microservices): application divided into smaller, specialized entities
- Solution to **monolithic** application design (single entity)
- Monolithic problems: long deployment times, large codebase, modifications cause instability
- Microservices advantages:
  - Smaller, specialized elements; each manages own database, logs, authentication
  - Use **microservices APIs** and **RESTful APIs**
  - Easier code updates with new features
  - Teams can use different programming languages
  - Components scale independently

---

## Objective 2 - Cloud Computing Security

### Cloud-Based Security

#### Virtual Security Appliances
- **Cloud firewall**: virtual software examining traffic into and out of cloud
  - Also called public cloud firewall, next-gen firewall, virtual firewall
  - Advantages over physical appliance: scales quickly
  - Cost consideration: hourly rate; micro-segmented networks need separate firewalls per segment
- **Secure web gateway (SWG)**: combines URL examination, web app monitoring, SSL traffic analysis, DLP, and SIEM alerts
  - Can be placed on endpoints, at the edge, or in the cloud

#### Cloud Access Security Broker (CASB)
- **CASB**: software tools/services between enterprise on-prem infrastructure and cloud provider infrastructure
- Acts as gatekeeper; ensures enterprise security policies extend to cloud data
- Enforces encryption policies; cloud-based DLP extends policies to cloud data

#### Secure Access Service Edge (SASE)
- **SASE** ("sassy"): convergence of several security services into a single cloud-delivered service model
- Identifies users/devices, applies policy-based security, delivers secure access
- Components: SWG, CASB, **zero-trust architecture (ZTA)**, WAN technologies
- **Security services edge (SSE)**: subset of SASE with only security components (no WAN)

### Cloud Vulnerabilities

| Security Issue | Description |
|---|---|
| **Unauthorized access to data** | Improper configurations leave data exposed |
| **Lack of visibility** | Limited/no visibility into cloud provider's security mechanisms |
| **Insecure APIs** | Threat actors exploit vulnerable APIs |
| **Compliance regulations** | Difficult to know where data is, who accesses it, how it's protected |
| **System vulnerabilities** | Complex networks and multiple third-party platforms |

#### Responsibility Matrix Confusion
- **Responsibility matrix**: table showing which security duties belong to organization, cloud provider, or both
- Varies by cloud model (IaaS, PaaS, SaaS)
- Misunderstanding leads to cloud misconfigurations (62% of professionals cite as biggest cloud risk)

#### Lack of Cloud Conceptual Model
- Physical networks map neatly to OSI seven-layer model
- In cloud: provider manages physical infrastructure; customer sees only abstract virtual layers
- Higher-level interactions (multiple accounts, VPCs, subnets) make security harder
- Proposed cloud conceptual models exist but none widely adopted

### Cloud Security Controls

#### Conduct Audits
- **Cloud security audit**: independent examination of cloud service controls
- Auditor evaluates security controls, privacy impact, availability, performance
- Verifies conformance to standards; important for federal agencies

#### Utilize Regions and Zones
- **High availability across zones**: duplicating processes across geographical areas
- **Availability Zone (AZ)**: one or more data centers within a Region; redundant power, networking, connectivity
- All AZs interconnected with high-bandwidth, low-latency fiber; within 60 miles of each other

#### Implement Secrets Management
- **Secrets management**: enables strong security for microservices-based architecture
- Provides central repository and single source to manage, access, and audit secrets

| Feature | Description |
|---|---|
| **Limited and automated replication** | Secret data stored in user-specified or provider-designated regions |
| **Secret-specific versioning** | Secret pinned to specific code version |
| **Audit logging** | Every interaction generates audit entry for abnormal access detection |
| **Default encryption** | AES-256-bit encryption at rest and in transit |
| **Extensibility** | Integrates into other existing secrets management systems |

#### Enforce Functional Area Mitigations

| Functional Area | Control | Description |
|---|---|---|
| Storage | **Permissions** | Enforce actions on stored data (edit, delete, copy) |
| Storage | **Encryption** | Encrypt data at rest in cloud |
| Storage | **Replication** | Multiple copies across regions/zones for high availability |
| Network | **Virtual networks** | VPC connecting services/resources via secure encrypted private network |
| Network | **Public and private subnets** | Public subnet for web servers; private subnet for back-end servers |
| Network | **Segmentation** | Rules for services between accessible zones |
| Network | **API inspection** | Automated authentication, authorization, encryption, compliance of APIs |
| Compute | **Security groups** | Segment computing resources into logical network perimeters |
| Compute | **Dynamic resource allocation** | Deprovision resources when no longer needed |
| Compute | **Instance awareness** | Security appliances differentiate between cloud app instances |
| Compute | **VPC endpoint** | Attach endpoint policy controlling access to service |

#### Hybrid Cloud Considerations
- **Hybrid cloud considerations**: security challenges from spanning public and private spaces
- Advantages: secure sensitive data in private cloud; less-sensitive in public; avoid single point of failure; comply with privacy/sovereignty regulations
- Best practices:
  - Encrypt sensitive data and traffic between clouds; inspect all encrypted traffic
  - Monitor/audit configurations; use automation to keep configurations aligned
  - Run regular scans; secure all endpoints; enforce zero-trust security

---

## Objective 3 - Virtualization Security

### Defining Virtualization

#### What Is Virtualization?
- **Virtualization**: managing and presenting computer resources by function without regard to physical layout
- **Host virtualization**: entire OS environment simulated
- **Virtual machine (VM)**: simulated software-based emulation of a computer
  - **Host system**: OS installed on hardware; runs VM monitor program
  - **Guest systems**: foreign virtual OSes running applications
- Used to consolidate multiple physical servers into VMs on single physical computer
- Typical server utilizes only 10–15% of capacity; extensive use in cloud computing

#### Hypervisors
- **Hypervisor**: VM monitor program managing VM operating systems
  - Uses code in software/firmware to allocate resources in real time
- **Type I hypervisor**: runs directly on hardware ("native" or "bare metal")
- **Type II hypervisor**: runs on host operating system like a regular application

#### Containerization
- **Containerization**: reduced instance of virtualization
- Container holds only necessary OS components (binary files, libraries) for specific application
- Containers share binary files/libraries; reduce storage/RAM; start faster
- Easily moved between computers

#### Virtual Desktop Infrastructure (VDI)
- **VDI**: running user desktop inside remote VM on server
- Personalized desktops available on any computer/device that can access server
- Provides flexibility (e.g., Linux desktop on Mac via Windows server)
- Centralized management; reduced support costs

### Advantages of Virtualization
- New VMs quickly available (**host availability**)
- Resources easily expanded/contracted (**host elasticity**)
- Cost savings: single physical server runs multiple VMs
- Reduced electricity and cooling costs
- **Live migration**: VM moved to different physical computer with no user impact
  - VM state saved to shared storage; reinstalled on new computer
  - Used for maintenance and load balancing

### Infrastructure as Code

#### Software-Defined Network (SDN)
- **SDN**: virtualizes parts of physical LAN for quick reconfiguration
- Separates **control plane** from **data plane**
  - Control plane: SDN servers performing routing, security checks, defining data flows
  - Data plane: switches managing flow tables created by controller
- Traffic first receives permission from SDN controller; once approved, route computed and entries added to switches
- Uses standardized protocol and API

#### Software-Defined Wide Area Network (SD-WAN)
- **SD-WAN**: virtualized service connecting and extending enterprise WAN networks over large distances
- Based on software; handles different traffic types and conditions in real time
- Better security and reliability than traditional WANs

#### Software-Defined Visibility (SDV)
- **SDV**: framework allowing automation of critical security functions
- Automates: dynamic response to threats, traffic configuration adjustments, IT operations management
- Relies on **RESTful APIs** (GET, PUT, POST, DELETE)

### Security Concerns for Virtual Environments

#### VM Security Advantages
- Test security updates in VM before production deployment
- Save **snapshot** of VM state for later reload
- **Security control testing** using simulated network environment
- Security segregation and isolation between VMs
- **Sandboxing**: test suspicious programs in isolated VM

#### VM Security Concerns
- Not all hypervisors have necessary security controls; compromised hypervisor risks multiple VMs
- Traditional security tools don't always adapt well to VMs; use "virtualized" versions
- VMs must be protected from outside networks and other VMs on same physical computer
- **VM escape**: VM breaks out of contained environment and interacts with host OS
  - Critical to have VM escape protection
- **Resource reuse vulnerability**: improperly flushed physical resources allow second VM to access first VM's data

#### Virtual Machine Sprawl
- **Virtual machine sprawl**: widespread proliferation of VMs without proper oversight or management
- Dormant guest OS may lack security updates
- **Virtual machine sprawl avoidance**: regular audits, good naming conventions, periodic cleanup, virtual machine manager

### Container Security
- Use nonprivileged user accounts for container-based processes
- Use trusted images (compromised image circumvents security)
- Use tools to harden hosts: **Security-Enhanced Linux (SELinux)**
  - Security architecture for Linux with access control lists and security policies
  - Originally developed by NSA; later integrated into Linux kernel

---

## Key Terms

- **centralized** — traditional model with equipment located locally
- **cloud computing** — on-demand network access to shared computing resources
- **cloud specific vulnerabilities** — security challenges unique to cloud environments
- **containerization** — reduced virtualization holding only necessary OS components
- **decentralized** — computing taking place in multiple locations
- **hardening cloud infrastructure** — applying controls to reduce cloud vulnerabilities
- **hybrid cloud considerations** — security challenges from spanning public and private clouds
- **infrastructure as code** — instances of virtualization (SDN, SD-WAN, SDV)
- **microservices** — application divided into smaller, specialized entities
- **on-premises** — computing resources on organization's campus
- **resource reuse** — vulnerability when physical resources not properly flushed between VMs
- **responsibility matrix** — table showing security duties between organization and cloud provider
- **secure access service edge (SASE)** — convergence of security services into cloud-delivered model
- **Security-Enhanced Linux (SELinux)** — Linux security architecture with ACLs and policies
- **serverless** — cloud infrastructure where provider handles all server management
- **software-defined network (SDN)** — virtualizes LAN by separating control and data planes
- **software-defined wide area network (SD-WAN)** — virtualized WAN service over large distances
- **third-party vendors** — external service providers for cloud management
- **virtualization** — managing computer resources by function without regard to physical layout
- **VM escape** — VM breaking out to interact with host operating system

---

## Review Questions

1. Which of the following is NOT a characteristic of cloud computing?
   a. Metered services
   b. Delayed elasticity ✓
   c. On-demand self-service
   d. Universal client support

2. Alois is creating a report for his team about the cost savings associated with cloud computing. Which of the following would NOT be included in his report on the cost savings?
   a. Reduction in broadband costs ✓
   b. Resiliency
   c. Scalability
   d. Pay-per-use

3. Lyam is completing a requisition form for the IT staff to create a type of cloud that would only be accessible to other HR managers like Lyam who are employed at manufacturing plants. The form asks for the type of cloud that is needed. Which type of cloud would best fit this need?
   a. Public cloud
   b. Group cloud
   c. Hybrid cloud
   d. Community cloud ✓

4. Mael is working on a project to deploy automated guided vehicles on the industrial shop floor of the manufacturing plant in which he works. What location of computing would be best for this project?
   a. Remote
   b. Edge
   c. Off-premises
   d. Fog ✓

5. Alderic is frustrated that his company is using so many different cloud services that span multiple cloud provider accounts and even different cloud providers. He wants to implement a technology to give full control and visibility over all the cloud resources, including network routing and security. What product does he need?
   a. Thin virtual visibility appliance (TVVA)
   b. SWG
   c. CASB
   d. Transit gateway ✓

6. What does the term "serverless" mean in cloud computing?
   a. The cloud network configuration does not require any servers.
   b. Server resources of the cloud are inconspicuous to the end-user. ✓
   c. Servers are run as VMs.
   d. All appliances are virtual and do not interact with physical servers.

7. Arsene has been given a project to manage the development of a new company app. He wants to use a cloud model to facilitate the development and deployment. Which cloud model should he likely choose?
   a. SaaS
   b. XaaS
   c. IaaS
   d. PaaS ✓

8. Which cloud model requires the highest level of IT responsibilities?
   a. IaaS ✓
   b. SaaS
   c. PaaS
   d. Hybrid cloud

9. The CEO is frustrated by the high costs associated with security at the organization and wants to look at a third party assuming part of their cybersecurity defenses. Emeric has been asked to look into acquiring requests for proposals (RFPs) from different third parties. What are these third-party organizations called?
   a. MXIAs
   b. MPSs
   c. MSSPs ✓
   d. MSSOs

10. Which of the following is NOT true about microservices?
    a. It is a solution to monolithic application design by dividing it into smaller entities.
    b. It is also called cloud-native microservices.
    c. It is used when the application is developed locally and then imported into the cloud. ✓
    d. The division of the application is not by technical processes.

11. Which of the following is NOT correct about high availability across zones?
    a. In a cloud computing environment, reliability and resiliency are achieved through duplicating processes across one or more geographical areas.
    b. An Availability Zone (AZ) is one or more data centers within a Region, each with redundant power, networking, and connectivity.
    c. They are more highly available, fault tolerant, and scalable than would be possible with a single data center.
    d. They require that specific security appliances be located on-prem so that the local data center can be considered as a qualified Zone. ✓

12. Which of these is NOT created and managed by a microservices API?
    a. User experience (UX) ✓
    b. Database
    c. Logs
    d. Authentication

13. Which of the following is true about secrets management?
    a. It does not provide a central repository.
    b. It can only be used on-prem for security but has a connection to the cloud.
    c. It requires AES-512. ✓ (Note: book says AES-256, so this is the false statement — marked as answer)
    d. It cannot be audited for security purposes.

14. Based on a common responsibility matrix, which of the following is a cloud service provider NOT responsible for?
    a. Devices ✓
    b. Physical hosts
    c. Physical datacenters
    d. Physical network

15. Which of the following includes ZTA?
    a. SWG
    b. CASB
    c. SASE ✓
    d. RCSC

16. Which type of hypervisor runs directly on a computer's hardware?
    a. Type I ✓
    b. Type II
    c. Type III
    d. Type IV

17. Which of the following is NOT correct about containers?
    a. Containers start more quickly.
    b. Containers reduce the necessary hard drive storage space to function.
    c. Containers require a full OS whenever APIs cannot be used. ✓
    d. Containers include components like binary files and libraries.

18. Which of the following virtualizes parts of a physical local network?
    a. SDN ✓
    b. SDV
    c. VDI
    d. SD-WAN

19. Which of the following will NOT protect containers?
    a. Use a hardened OS.
    b. Use reduced-visibility images to limit the risk of a compromise.
    c. Only use containers in a protected cloud environment.
    d. Eliminate APIs. ✓

20. What do SDN, SD-WAN, and SDV all have in common?
    a. They were all developed in the 1970s.
    b. They are all infrastructure as code. ✓
    c. They require a public cloud.
    d. Specific REST-R-APIs must be used with each of them.
