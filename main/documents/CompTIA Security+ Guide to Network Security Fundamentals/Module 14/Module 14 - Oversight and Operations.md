---
created: 2026-08-25 20:22:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 14 — governance, compliance, security operations, automation, orchestration, threat hunting, and AI
mod.: 2026-08-25 20:22:00
aliases:
  - security+ module 14
  - oversight and operations
tags:
  - study/security-plus
  - study/security-plus/module-14
---

# Module 14 - Oversight and Operations

## Objectives

1. [[#Objective 1 - Governance and Compliance|Describe information security governance and compliance]]
2. [[#Objective 2 - Security Operations|Explain the security operations of automation, orchestration, and threat hunting]]
3. [[#Objective 3 - Artificial Intelligence|Describe how artificial intelligence is used in information security]]

---

## Objective 1 - Governance and Compliance

### Governance

#### What Is Governance?
- **Governance**: structures, systems, and practices an organization has in place to **assign**, **oversee**, and **report**
  - **Assign**: decision-making responsibilities, how decisions are made, strategic direction
  - **Oversee**: delivery of services, implementation of policies/plans/programs/projects, monitoring and mitigation of risks
  - **Report**: performance toward intended results; using that information to drive improvements and corrective actions (monitoring and revising)

##### Principles of Good Governance

| Principle | Explanation |
|---|---|
| **Accountability** | Obligation of an individual/group/organization to answer for a responsibility that has been conferred |
| **Leadership** | "Setting the tone" — plays crucial role in encouraging personnel to embrace good governance practices |
| **Integrity** | Acting impartially and ethically; compliance with legislation, regulations, policies; instilling high standards of professionalism |
| **Stewardship** | Responsibly looking after resources on behalf of the organization; maintaining or improving capacity to serve public interest |
| **Transparency** | Decisions and actions are open; stakeholders have access to full, accurate, and clear information on public matters |

### Governance Architectures

#### Bodies

| Body | Scope | Description |
|---|---|---|
| **Board** | Internal | Internal directors who approve strategic organizational goals and policies |
| **Committee** | Internal | Board governance committee managing governance issues |
| **Government entity** | External | National governments direct organizations through governance directives |
| **Regulatory** | External | Distribute and enforce government directives |
| **Legal** | Internal | Internal corporate legal departments interpret internal and external governance policies |
| **Industry** | External | Different industries create and audit governance policies for member organizations |

- Can be **centralized** (all authority in single group) or **decentralized** (planning/decision-making distributed to smaller groups)

#### Roles

| Role | Description | Duties | Example |
|---|---|---|---|
| **Data privacy officer (DPO)** | Manager overseeing data privacy compliance and risk | Ensures enterprise complies with data privacy laws and own policies | Decides users can access SALARY.XLSX |
| **Custodian/steward** | Individual to whom day-to-day actions are assigned by owner | Periodically reviews security settings; maintains records of access | Sets and reviews security on SALARY.XLSX |
| **Owner** | Person responsible for the information | Determines level of security needed; delegates security duties | Determines SALARY.XLSX can be read only by managers |
| **Controller** | Principal party for collecting data | Acquires user consent, stores data, manages consent/revoking access | Gathers data for SALARY.XLSX; identifies storage |
| **Processor** | Proxy acting on behalf of data controller | Holds/processes personal data for third party; does not make decisions about data use | Manages SALARY.XLSX on behalf of controller |

- **Object**: specific resource (file, hardware device)
- **Subject**: user or process functioning on behalf of user attempting to access an object
- **Operation**: action taken by subject over object

### Governance Mechanisms

#### Policies
- **Policy**: formal statement outlining specific requirements or rules based on governing body decision
- Outlines principles to be followed; addresses overall purpose of organization
- Manager view: set of management statements defining philosophy of safeguarding information
- Security technician view: technical configuration settings in a system
- **Not** a motivational tool — research shows specific elements do not impact user behavior

##### Types of Policies
- **Acceptable-use policy (AUP)**: defines actions users may perform while accessing systems/networking equipment
  - Covers employees, vendors, contractors, visitors (each with different privileges)
  - Typically covers all computer use including mobile devices
- **Business continuity policies**
- **Disaster recovery policies**
- **Incident response policies**
- **Software development lifecycle (SDLC) policy**: outlines how applications should be developed
- **Group Policy**: Microsoft Windows process of assigning privileges to groups of users
  - Local Group Policy: individual computer; Domain Group Policy: all users in domain

#### Procedures
- **Procedure**: detailed mandatory steps to comply with a policy; informs employees how to carry out (implement) a policy
- Often logically numbered steps or checklists
- **Incident response playbook**: lists specific actions to take for threats

##### Onboarding and Offboarding
- **Onboarding**: tasks associated with hiring new employee (NDA signing, computer setup, email, user accounts, folders)
- **Offboarding**: actions when employee leaves (disable accounts immediately, backup files, archive email, forward email, hide from address book)
- **Orphaned accounts**: user accounts that remain active after employee has left — serious security risk
- **Account expiration**: explicit (set date) or based on days of inactivity

#### Standards
- **Standard**: specifies uniform uses of specific technologies or settings for secure configurations
- Can be internal or from external third party

##### PCI DSS Requirement 11 Standards

| Standard | Description | Frequency |
|---|---|---|
| 11.1 | Test for wireless access points; detect authorized/unauthorized | Quarterly |
| 11.2 | Run internal/external vulnerability scans; rescans until passing | At least quarterly and after significant network change |
| 11.3 | Develop/implement penetration testing methodology | At least annually and after significant upgrade/modification; service providers every 6 months |

#### Guidelines
- **Guideline**: provides general guidance and support for policies, standards, or procedures
- **Voluntary** (unlike policies, standards, and procedures which are mandatory)

### Compliance

#### Defining Compliance
- **Compliance**: process of ensuring organization adheres to laws and regulations related to information security and user data privacy
- Regulatory examples: GDPR (European citizens), PCI DSS (payment cards), HIPAA (healthcare)

#### Compliance Monitoring
- **Compliance monitoring**: quality assurance tests to determine how well business operations meet security regulations/standards
- Ensures **due care** (taking reasonable steps to secure/protect assets) and **due diligence** (identifying and mitigating risks from third parties)

##### Internal Compliance Monitoring
- Dedicated compliance team tracks compliance using **automation compliance tools**
- Tools categorize, collect, and analyze data; generate alerts on spikes/drops
- Generate internal compliance reports for auditors

##### External Compliance Monitoring
- Third-party entities examine protections and create external compliance report
- Serve as official **attestation** (verification of truth/authenticity)
- Require statement acknowledging organizational responsibility for internal controls

### Securing Data Privacy Through Compliance

#### Types of Data Collection
- **Overt and legitimate**: organization has valid business need; data requested openly
- **Concealed and questionable**: collected secretly without clear knowledge/permission; no clear business case

##### Data Trail and Trackers
- Users leave a "data trail" — digital record of activity
- **Trackers**: embedded in virtually every app (average: six per app); collect interaction data and location
- Volume of compiled data grows exponentially

#### Issues with Private Data Collection

| Issue | Explanation |
|---|---|
| Secret gathering | Users have no formal rights to find out what's gathered, who gathers it, or how it's used |
| Accuracy unverifiable | Users can't correct or control what's gathered; inaccurate data may lead to erroneous decisions |
| Identity theft impact | Victims have information added by thieves; no right to see/correct |
| Unknown factors | Ratings combine thousands of factors (race, religion, age, income, etc.) — impact unknown |
| Missing consent | Privacy policies like "may share for marketing" aren't clear informed consent |
| Important decisions | Data used for jobs, credit, insurance, identity verification |
| Discrimination | Targeted ads can perpetuate harmful stereotypes |

#### Current Data Protections
- **Data subjects**: any living individual whose personal data is collected and stored
- **Right to be forgotten** (EU): data subjects have legal right to have private data erased (~30 days)
- U.S. has no "right to be forgotten" — protections are primarily industry regulations
- Regulations outline controller vs. processor tasks, data inventory, and retention

---

## Objective 2 - Security Operations

### Security Operations Center (SOC)
- **SOC** ("sock"): function responsible for detecting, analyzing, and responding to cybersecurity incidents
- Members handle: proactive monitoring, incident response/recovery, remediation, compliance, coordination

### Automation

#### Need for Security Automation
- Must collect global threat intelligence across all attack vectors
- Finding correlations from multiple data sources improves accuracy, reduces false positives
- Data must scale to meet ever-increasing threats
- Information security has traditionally been more manual than automated

#### Benefits of Security Automation

| Benefit | Explanation |
|---|---|
| **Produce time efficiency** | Improve productivity by reducing time to complete tasks |
| **Enforce baselines** | Ensure required baselines are imposed |
| **Distribute standard infrastructure configurations** | Distribute configurations to all devices without missing settings |
| **Securely scale** | Adding appliances performed more securely through automation |
| **Improve staff retention** | Reduce stress and "burnout" fatigue from sifting through massive data |
| **Reduce reaction time** | Dramatically decrease time needed to react to an attack |
| **Generate workforce multiplier** | Give staff ability to be more productive |

##### Risks of Automation
- **Complexity**: interconnecting appliances introduces complications
- **Ongoing support**: requires continual monitoring
- **Cost**: more expensive
- **Technical debt**: equipment problems can cause additional future problems
- **Single point of failure**: overreliance on automation; issue could cause entire process to cease

#### Use Cases for Security Automation

##### Enhanced Software Development

| Process | Description | Advantage |
|---|---|---|
| **Continuous integration (CI)** | Developers merge changes to main branch as often as possible | Problems identified from smaller code segments |
| **Continuous delivery (CD/CDE)** | Automatically deploy all code changes to testing/production after compilation | Allows deployment daily/weekly based on business needs |
| **Continuous deployment (CD)** | Every change passing all production pipeline stages immediately released | No human intervention needed; excellent feedback loop |

##### Integrations and Application Programming Interfaces (APIs)
- **Integration platform as a service (iPaaS)**: automated tools for connecting software applications in different environments
- APIs provide direct access to data and entry points to application functions
- Relieves developer from writing code for specific hardware/software
- **API attack**: exploiting vulnerabilities in APIs; can have broad impact

##### Scripting
- **Script**: short "snippet" of code ideal for automation
- Features: simple program invocation, less strict language requirements (no type system), no variable declaration requirement
- Runtime usually included in OS installation
- Common languages: JavaScript, PHP, Python, Ruby

##### Guardrails
- **Security guardrails**: automations that constantly watch cloud deployments, find deviations from baselines, and can automatically remediate issues
- Leverage cloud APIs and automation; do not add friction to development processes

##### Improved Provisioning
- **Provisioning**: process of creating and setting up IT infrastructure
- Traditional: manual process with managerial approval and technical implementation (weeks to months)
- **Automated user provisioning**: automatically grants/manages users' access based on positions and permission levels
  - Onboarding: identity management platform assigns role and access
  - Position change: accounts and access updated automatically
- **Resource automation provisioning**: system-level provisioning

##### Security Groups
- **Security groups**: virtual firewall controlling all inbound/outbound traffic to cloud resource
- Associated with network interfaces; changes reflected immediately
- Example: quickly deny ingress traffic from threat actors (disabling services and access)
- Not highly granular (can't restrict by specific IP address)

##### Other Use Cases
- **Escalation**: rapid detection of threat incident for immediate elevation (automatic escalation)
- **Continuous integration and testing**: automation enables continuous testing (vs. manual "one-and-done")
- **Ticket creation**: automated ticket creation from security events; eliminates manual analysis time

### Orchestration
- **Security orchestration**: automation and combination of many different individual tasks and processes
- Automation = single task; orchestration = entire process (workflow) automated
- Coordinates hardware, software, middleware, and services across multiple platforms
- Purpose: streamline/repeatable processes, eliminate redundancies, speed completion, reduce errors

#### SOAR Platform
- **Security orchestration, automation, and response (SOAR)**: combination of software programs/tools synthesizing and automating security operations, threat intelligence, and incident response
- Can automatically block IP addresses during brute-force attacks
- Displays metrics like "Dollars saved"

### Threat Hunting

#### What Is Threat Hunting?
- **Threat hunting**: proactive, repetitive (iterative), and predominantly human identification of cyber invasion that has evaded existing security controls
- Assumes network is already infected; attackers are currently inside (not trying to enter from outside)
- Described as "incident response—but without the incident!"

##### Security Roles Comparison

| Role | Role Type | Goal | Task | Driving Force | Timeframe |
|---|---|---|---|---|---|
| **Incident responder** | Reactive | Secure environment after alarm | Minimize attack impact through formal process | Business continuity | Immediate |
| **Penetration tester** | Proactive | Secure environment through controlled offensive exercises | Mimic threat actor actions | Uncover vulnerabilities | Soon |
| **Threat hunter** | Proactive | Identify suspicious activity before alarm | Seek evidence of malicious behavior | Prevent infection from spreading | Longer |

#### Levels of Threat Hunting

| Level | Name | People | Processes | Tools |
|---|---|---|---|---|
| 1 | **Initial** | Existing SOC personnel | Ad-hoc hunts with little data | Standard SOC reactive tools |
| 2 | **Managed** | Volunteer threat hunter | Basic threat feeds with IoCs; hunts occasionally | Text string searching; automatic IoC matching |
| 3 | **Defined** | Dedicated threat hunter | Formal hunting process; regular data collection | Statistical analysis techniques |
| 4 | **Quantitatively Managed** | SOC analysts rotated into team | Frequent hunts; moderate data collection | Dashboards and visualization tools |
| 5 | **Optimized** | Threat-hunting teams integrated across SOC | Continuous hunts; data shared across security community | Machine learning |

#### Threat-Hunting Process and Tactics

1. **Select the attack model**: decide how envisioning threat actor process; profile threat actors and activities
2. **Identify most concerning threats**: consider variety of factors; go through each phase of chosen model
3. **Create a calendar**: how frequently to hunt for specific threats; high-impact activities hunted more frequently
4. **Generate a hypothesis**: tentative assumption to be tested
   - Example: "If network is infected with WannaCry ransomware, we will see increase in rate of file renaming"
5. **Investigate the hypothesis**: follow up using different tools and techniques
6. **Act on results**: if false — no indication based on specific hypothesis; if true — turn over to SOC; automate successful hunts

---

## Objective 3 - Artificial Intelligence

### Defining AI

#### Relationships

| Term | Description |
|---|---|
| **Data analytics** | Fixed process examining large data sets to draw conclusions; relies on human interaction to query data, identify trends, test assumptions |
| **Artificial intelligence (AI)** | Subset of data analytics; autonomous — works without immediate/continual human assistance; creates predictive models; iterative and dynamic |
| **Machine learning (ML)** | Subset of AI; uses statistical techniques to give computer systems ability to "learn" and improve using data rather than explicit programming |

- AI refers to technologies that can understand and act by themselves based on acquired and derived information

#### Types of AI Systems

| Type | Description |
|---|---|
| **Assisted intelligence** | Widely available; improves what people/organizations already do |
| **Augmented intelligence** | Emerging; enables people/organizations to do things not possible otherwise |
| **Autonomous intelligence** | Being developed for future; machines act entirely on their own (e.g., self-driving vehicles) |

### AI Uses in Information Security

#### Security Challenges AI Addresses
- Hundreds/thousands/hundreds of thousands of endpoints per organization
- Large numbers of daily vulnerabilities including unknown zero-days
- Massive amounts of security-related data generated hourly
- Serious shortage of trained security personnel

#### AI Security Tasks

| Task | Explanation |
|---|---|
| **Analyze controls** | Insight into current controls, strengths, weaknesses; identify gaps |
| **Reduce threat exposure** | Up-to-date global/industry-specific threat information for prioritization |
| **Conduct asset inventory** | More accurate inventory of devices, users, applications; categorization and business criticality measurement |
| **Perform breach risk prediction** | Predict how/where organization is most likely to be breached based on asset inventory, threat exposure, controls |
| **Manage incident response** | Improved context of attack to prioritize and quickly respond |
| **Provide descriptive explanations** | Help provide understanding of security system impact to stakeholders (CISO, auditors, CIO, CEO, board) |

### Security AI Risks

#### Operational Risks
- Needs huge volumes of high-quality data (many organizations lack sufficient data)
- Generates too many false positives
- Hard to "tune" for specific needs of individual customers (especially smaller organizations)
- Lack of transparency in decision-making
- Algorithmic models degrade over time without proper maintenance

#### Adversarial Artificial Intelligence

| Attack | Description |
|---|---|
| **Compromise the algorithms** | AI-powered security applications have vulnerabilities; could be attacked and algorithms altered to ignore attacks (like rootkit for OS) |
| **Taint ML training data** | Attackers alter training data to produce false negatives and cloak themselves |
| **Use AI maliciously** | Threat actors use AI to break through defenses and develop mutating malware that changes structure to avoid detection |

---

## Key Terms

- **acceptable-use policy (AUP)** — defines actions users may perform while accessing systems
- **acknowledgment** — formal recognition of something
- **attestation** — verification of truth or authenticity
- **automated provisioning** — automatically granting/managing user access
- **automation compliance tools** — tools categorizing/collecting/analyzing compliance data
- **board** — internal directors approving strategic goals and policies
- **centralized** — all authority vested in single group
- **committee** — board governance subset managing governance issues
- **complexity** — complications from interconnecting appliances in automation
- **compliance** — ensuring organization adheres to laws and regulations
- **compliance monitoring** — quality assurance tests for regulations/standards
- **continuous integration and testing** — automation enabling continuous testing
- **contractual impacts** — suspending or terminating contracts for noncompliance
- **controller** — principal party for collecting data
- **cost** — expense of automation
- **custodian/steward** — individual assigned day-to-day actions by owner
- **data inventory** — monitoring collected data
- **data subjects** — living individuals whose personal data is collected
- **decentralized** — planning/decision-making distributed to smaller groups
- **disabling services and access** — denying ingress traffic from threat actors
- **distribute standard infrastructure configurations** — automation distributing configurations to all devices
- **due care** — taking reasonable steps to secure/protect assets
- **due diligence** — identifying and mitigating risks from third parties
- **enabling services and access** — granting access based on positions/permission levels
- **enforce baselines** — ensuring required baselines are imposed
- **escalation** — rapid detection for immediate elevation
- **external compliance monitoring and reporting** — third-party compliance examination
- **fines** — monetary penalties for noncompliance
- **generate workforce multiplier** — automation giving staff ability to be more productive
- **global body** — worldwide scope governance body
- **global data protections** — protections to which all nations adhere
- **governance** — structures, systems, practices for assigning, overseeing, reporting
- **government entity** — national governments directing through governance directives
- **guardrails** — automations watching cloud deployments for deviations
- **guideline** — voluntary general guidance for policies/standards/procedures
- **improve staff retention** — reducing burnout fatigue through automation
- **industry** — industry-created governance policies
- **integrations and application programming interfaces (API)** — automated tools connecting software applications
- **internal compliance monitoring** — organization-performed compliance testing
- **internal compliance report** — report verifying compliance for auditors
- **legal** — internal departments interpreting governance policies
- **legal implications** — ramifications of violating data protections
- **local/regional body** — governance body covering immediate area
- **local/regional data protections** — state-level privacy laws
- **loss of license** — withdrawal of permit to function
- **monitoring and revising** — using performance information for improvements
- **national body** — governance body covering entire nation
- **national data protections** — country or group of countries protections
- **noncompliance** — failure to follow compliance standards
- **offboarding** — actions when employee leaves enterprise
- **onboarding** — tasks associated with hiring new employee
- **ongoing support** — continual monitoring required by automation
- **orchestration** — automation and combination of many different tasks/processes
- **owner** — person responsible for information
- **ownership** — legal possession and control of data
- **playbook** — list of specific actions to take for threats
- **policy** — formal statement outlining requirements or rules
- **procedure** — detailed mandatory steps to comply with policy
- **processor** — proxy acting on behalf of data controller
- **produce time efficiency** — reducing time to complete tasks
- **reduce reaction time** — decreasing time to react to attacks
- **regulatory** — agencies distributing/enforcing government directives
- **reputational damage** — negative perceptions of organization
- **resource automation provisioning** — system-level provisioning
- **retention** — how long data should be kept
- **right to be forgotten** — EU legal right to have private data erased
- **sanctions** — other penalties such as withholding payments
- **securely scale** — adding appliances more securely through automation
- **security groups** — virtual firewalls controlling cloud resource traffic
- **single point of failure** — overreliance causing automation failure
- **software development lifecycle (SDLC) policy** — outlines how applications should be developed
- **standard** — specifies uniform uses of technologies/settings
- **technical debt** — future problems from unaddressed equipment issues
- **threat hunting** — proactive, iterative, human identification of cyber invasion
- **ticket creation** — automated ticket creation from security events
- **user automation provisioning** — automatic user access management

---

## Review Questions

1. Which of the following is correct about security automation?
   a. Security operations have been more manual than automated for many years. ✓
   b. Security automation requires both AI and ML.
   c. Security automation has been used since the very beginning of cybersecurity.
   d. Threat hunting relies heavily on cybersecurity automation.

2. Alois is explaining to his parents his new position in a SOC. Which of the following would Alois NOT say about a SOC?
   a. It houses the IT security team.
   b. It is responsible for detecting and analyzing cybersecurity incidents.
   c. It uses strictly automatic processes. ✓
   d. A SOC responds to cybersecurity incidents.

3. Matheo is explaining to a new intern about the security automation used in the SOC. Which of the following would he NOT say regarding security automation?
   a. Using manual cybersecurity processes by a SOC will tip the balance in favor of attackers.
   b. Modern cyberattacks are highly automated so defenses need to be automated.
   c. Cybersecurity automation is now required by most certification bodies. ✓
   d. Time spent on manual processes allows threat actors time to spread their malware.

4. What is data correlation?
   a. Finding linkages from multiple data sources. ✓
   b. A requirement for using ML.
   c. A dated technology no longer used due to the introduction of SIEM.
   d. Using a minimum of three external and three internal data sources to understand a zero-day attack.

5. Which of the following is NOT correct about governance?
   a. Governance refers to the structures, systems, and practices an organization has in place to assign, oversee, and report.
   b. Governance is involved in assigning decision-making responsibilities, defining how decisions are to be made, and establishing the organization's strategic direction.
   c. Governance is not concerned with overseeing the delivery of services; the implementation of its policies, plans, programs, and projects; and the monitoring and mitigation of risks. ✓
   d. Governance involves reporting on performance toward achieving intended results and then using that performance information to drive ongoing improvements and corrective actions.

6. Which of the following is composed of internal directors who approve strategic organizational goals and policies?
   a. Panel
   b. Committee
   c. Board ✓
   d. Council

7. Who is the principal party for collecting data?
   a. Custodian/steward
   b. Owner
   c. Controller ✓
   d. Processor

8. Which policy defines the actions users may perform while accessing systems and networking equipment?
   a. ACXT
   b. RSRS
   c. BAC
   d. AUP ✓

9. Which policy outlines how applications should be developed?
   a. SORA
   b. SCAP
   c. SDLC ✓
   d. SARC

10. Which of the following is voluntary and not mandatory?
    a. Guideline ✓
    b. Policy
    c. Standard
    d. Procedure

11. Lyam is researching scripting. Which of the following is NOT correct about scripting?
    a. JavaScript, PHP, Python, and Ruby are common scripting languages.
    b. The language runtime of a scripting language is usually included in the installation of the OS.
    c. Scripting has features not found in formal programming languages.
    d. Scripting should not be used for automation. ✓

12. Which of the following is NOT correct about guardrails?
    a. Guardrails can automatically remediate issues.
    b. Guardrails add friction to slow down the development process. ✓
    c. Guardrails constantly watch cloud deployments.
    d. Guardrails leverage cloud APIs and automation.

13. What is another name for integrations and application programming interfaces?
    a. APIaaS
    b. PaaS
    c. SaaS
    d. iPaaS ✓

14. Which of the following involves the automation and combination of many different tasks and processes?
    a. Multitask combination (MTC)
    b. Cybersecurity automation
    c. Orchestration ✓
    d. Autoflow

15. Which of the following platforms can take immediate action when it detects a malicious action?
    a. SIEM
    b. SOAR ✓
    c. RSOC
    d. SAII

16. Which threat-hunting level hunts continuously and shares data across the security community?
    a. Managed
    b. Defined
    c. Quantitatively Managed
    d. Optimized ✓

17. Which of the following is NOT a risk associated with using AI in cybersecurity?
    a. Attackers can attempt to alter the training data that is used by ML in order to produce false negatives to cloak themselves.
    b. The time needed for AI to provide indicators of attacks (IoA) but not indicators of compromise (IoC) is considered too slow to be useful today. ✓
    c. Threat actors may turn to using AI for attacks in order to circumvent defenses.
    d. AI-powered security applications and their devices likewise have vulnerabilities that could be attacked and compromised so that threat actors could alter the algorithms to ignore attacks.

18. Which of the following is NOT a characteristic of threat hunting?
    a. Recursive ✓
    b. Predominantly human
    c. Iterative
    d. Proactive

19. AI is a subset of which domain?
    a. ML
    b. Data analytics ✓
    c. SOC
    d. Threat hunting

20. Which of the following is NOT an information security task that AI can perform?
    a. Perform breach risk prediction
    b. Conduct asset inventory
    c. Reduce threat exposure
    d. Configure controls ✓
