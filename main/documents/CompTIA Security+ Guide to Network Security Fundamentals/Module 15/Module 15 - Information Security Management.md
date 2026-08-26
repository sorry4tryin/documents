---
created: 2026-08-19 20:12:00
class:
  - document
description: CompTIA Security+ SY0-701 Module 15 — asset management, change management, risk management, third-party risk, and security awareness
mod.: 2026-08-19 20:12:00
aliases:
  - security+ module 15
  - information security management
tags:
  - study/security-plus
  - study/security-plus/module-15
---

# Module 15 - Information Security Management

## Objectives

1. [[#Objective 1 - Asset Protection|Explain asset protections]]
2. [[#Objective 2 - Risk Management|Describe risk management]]

---

## Objective 1 - Asset Protection

- **Asset**: any item that has a positive economic value
- Enterprise assets include people, physical items, and IT assets (hardware, software, data)

### Asset Management

- **Asset management**: coordinated activity of an organization to realize value from its assets
- Requires systematic governance and proper utilization in a cost-effective manner
- Referenced standard: ISO 55000:2014

#### Cybersecurity Asset Management (CAM)

- **Cybersecurity asset management (CAM)**: combines asset management with information security to identify assets on a continuous and real-time basis
- Identifies endpoints, servers, IoT devices, and cloud-based resources
- Uses vulnerability scanners to identify potential security gaps affecting each asset
- Introduces **Mean Time to Inventory (MTTI)**: metric to determine when incident response is lagging due to missing inventory information
- Without CAM, gaps exist between acquisition of new assets and recording those assets, leaving new assets unprotected

### Asset Management Lifecycle

- Lifecycle phases: Requirements Definition → Asset Planning → Asset Creation/Acquisition → Operations and Maintenance → Asset Monitoring → Renewal/Rehab → Disposal
- Costs throughout lifecycle include: initial acquisition, operating costs, inspections and condition assessments, preventative maintenance, corrective maintenance, rehabilitation, and disposal

### Selected Asset Management Tasks

#### Acquisition

- **Asset acquisition** (asset procurement): process of identifying and then securing an asset to support a business goal
- Starts with determining current and future needs; specifications are developed; approval granted; funding secured
- Two bidding processes:
  - **Standard bidding process**: solicits bids from qualified vendors before purchase; vendors submit proposals with detailed product information
  - **E-bidding process**: uses electronic bidding platforms; vendors submit bids online with pricing information only

#### Assignment

- **Asset assignment/accounting**: process of determining and recording ownership and classification of an asset
- Ownership based on which entity purchased the asset; can be transferred between departments
- Three classification factors:
  - **Convertibility/liquidity**: ease of converting asset to cash
    - **Current asset**: can be used up or turned into cash within one fiscal year
    - **Fixed asset**: long-term asset kept for more than a year
  - **Usage**:
    - **Operating asset**: needed for the primary business function
    - **Nonoperating asset**: not used daily but helps keep the business financially stable
  - **Physical existence**:
    - **Tangible asset**: can be touched (hardware, cash, equipment, property)
    - **Intangible asset**: has monetary value but no physical form (software, data, patents, intellectual property)

#### Tracking

- **Asset tracking**: tracing the location of tangible assets
- Three tracking methods: barcode labels, RFID tags, GPS tracking sensors
- **Inventory**: raw materials, works in progress, and finished goods available for sale that a business owns
- **Asset enumeration**: listing of assets by a seller of those assets (distinct from information security enumeration used in penetration testing)

#### Disposal

- Two-step process: **asset decommissioning** (withdraw from service) then **asset disposal** (physically remove)
- If asset can still be used, it may be sold; otherwise it is rendered unusable (**destruction**)
- **Data retention**: transfer valuable data to a different device before sanitization
- **Sanitization**: wiping clean or destroying the media on which data is stored
- Paper media destruction methods:
  - **Shredding**: cutting into small strips or particles (strip-cut, cross-cut, micro-cut)
  - **Burning**: lighting on fire
  - **Pulping**: breaking paper back into wood cellulose fibers after ink removal
  - **Pulverizing**: hammering paper into dust
- Electronic media destruction methods:
  - **Purging**: erasing using the OS "delete" command — data can still be retrieved with forensic tools; should be avoided
  - **Wiping**: overwriting disk space with zeros or random data
  - **Degaussing**: permanently destroys entire magnetic hard disk drive by eliminating the magnetic field
- **Certification**: verifying destruction for regulatory purposes (some techniques like degaussing cannot provide verification alone)

### Change Management

- **Change management**: systematic approach to dealing with adjustments and replacements within an organization
- Purpose: implement strategies for effecting change, controlling change, and adapting to change
- Requires verified process for: planning and testing change, communicating change, scheduling and implementing change, and documenting change

#### Need for Change Management

- Normal business processes (**standard operating procedures**) can impact information security:
  - **Approval process**: multilayer approvals can slow acquisition of security appliances
  - **Change in ownership or stakeholders**: affects how asset is used and perceived
  - **Implement impact analysis or test results**: can change how devices are configured
  - **Execute backout plan or maintenance window**: **backout plan** is procedures for rollback after a release; **maintenance window** is designated time for routine maintenance — both can impact security
- Routine technical processes with security impact:
  - **Changing allow lists/deny lists**: modifying permissions can impact security
  - **Modifying restricted activities**: changing restricted to permitted can have unforeseen consequences
  - **Experiencing downtime**: restart of devices may leave them out-of-sync
  - **Implementing service or application restarts**: can create gaps in security coverage
  - **Using legacy applications**: may have unpatched vulnerabilities
  - **Adjusting dependencies**: changing reliance between services can create security issues

#### Change Management Tools

- Small organizations: spreadsheets, flowcharts, Gantt charts
- Larger organizations: specialized change management software suites for digital change logs
  - Automatically update **updating diagrams** (flow illustrations of changes)
  - Indicate which **updating policies/procedures** need adjustment
- **Version control software**: tools for documentation and preventing simultaneous code changes; can track changes and back out when necessary

---

## Objective 2 - Risk Management

- **Risk**: a situation that involves exposure to some type of danger
- At a more advanced level: function of threats, the consequences of those threats, and the resulting vulnerabilities
- **Likelihood of occurrence**: how realistic the chance is that a given threat will compromise an asset

### Defining Risk

#### Threat Classifications

| Threat Category | Description | Example |
|---|---|---|
| Strategic | Affects long-term goals of the organization | Theft of intellectual property, loss of a major account |
| Compliance | Following or not following a regulation or standard | Breach of contract, not responding to new laws |
| Financial | Impact of financial decisions or market factors | Increase in interest rates, global financial crisis |
| Operational | Events impacting daily business | Fire, hazardous chemical spill, power blackout |
| Technical | Events affecting IT systems | DoS attack, SQL injection, virus |
| Managerial | Actions related to management of the organization | Long-term illness of president, key employee resigning |

#### Sources of Risk

- **Internal risk**: comes from within the organization (e.g., employee theft)
- **External risk**: from the outside (e.g., actions of a hacktivist)
- **Legacy systems**: risks from outdated hardware or software with unpatched vulnerabilities
- **Multiparty risk**: impact that vulnerabilities of one organization have on connected organizations downstream
- **Software compliance and licensing**: unauthorized use of software beyond license terms

### Analyzing Risks

- **Risk identification**: process to identify and assess factors that may jeopardize success of a project or reaching a stated goal

#### Methodology

- **Risk Control Self-Assessment (RCSA)**: methodology by which management and staff at all levels collectively work to identify and evaluate risks
- Goal: minimize biases and prejudices while integrating risk management into the culture
- Human biases that hinder risk identification:
  - **Aggregate bias**: inferring something about an individual using data describing broader population trends
  - **Anchoring bias**: holding on to a specific feature early in decision-making
  - **Availability bias**: perceiving likelihood of event based on how frequently heard about
  - **Confirmation bias**: making a decision before investigating, then only looking for supporting data
  - **Present bias**: discounting future risks in favor of immediate gratification
  - **Framing effect**: deciding on an option based on how choices are worded
  - **Fundamental attribution error**: viewing others' failures as part of their identity rather than contextual influences
- People tend to: overreact to intentional-action risks, underreact to accident/abstract/natural risks, overreact to immediate risks, underreact to long-term risks

#### Risk Assessment

- **One-time assessment**: scheduled assessment at a specific point in time
- **Ad hoc assessment**: done whenever necessary
- **Recurring assessment**: conducted on a calendar basis
- **Continuous assessment**: conducted year-round
- Two approaches:
  - **Qualitative risk analysis**: uses "educated guess" based on observation; assigns numeric value (1–10) or label (High, Medium, Low)
  - **Quantitative risk analysis**: more formal and systematic; uses historical data to create "hard" numbers

#### Risk Likelihood

- **Risk probability**: possibility that a risk will become a reality within a specific period of time
- Quantitative tools for predicting likelihood:
  - **Mean Time Between Failure (MTBF)**: average time until a component fails and must be replaced; total time measured divided by total number of failures
  - **Mean Time to Recovery (MTTR)**: average time to recover from a non-terminal failure
  - **Mean Time to Failure (MTTF)**: average time expected until first failure of a piece of equipment that cannot be repaired
  - **Failure in Time (FIT)**: reports expected failures per one billion hours of operation (used by semiconductor industry)
  - **Annualized Rate of Occurrence (ARO)**: probability that a risk will occur within a year
- Historical data sources: law enforcement agencies (crime statistics), insurance companies (risks faced and payouts), computer incident monitoring organizations (technology-related risks, failures, and attacks)

#### Risk Impact

- **Single Loss Expectancy (SLE)**: expected monetary loss every time a risk occurs
  - Formula: SLE = AV × EF
  - **Asset Value (AV)**: value of the asset
  - **Exposure Factor (EF)**: proportion of asset value likely to be destroyed by a particular risk (expressed as percentage)
- **Annualized Loss Expectancy (ALE)**: anticipated monetary loss expected for an asset due to risk over one year
  - Formula: ALE = SLE × ARO
- **Risk exposure factor**: probability of risk occurring multiplied by total loss on occurrence (potential for financial loss)

### Representing Risks

- **Risk reporting**: tools used to represent risks identified through risk assessment
- **Risk register**: list of potential threats and associated risks; often shown as a table providing a snapshot of vulnerabilities and risks
  - May include: **key risk indicators** (primary risk factors), **risk owners** (those responsible for the asset), **risk threshold** (maximum amount of risk that can be tolerated)
- **Risk matrix/heatmap**: visual color-coded tool that lists impact and likelihood of risks
  - Axes: relative impact (Catastrophic through Limited) and relative likelihood (Very High through Low)

### Managing Risks

- **Risk tolerance**: level of risk that an organization can accept per individual risk
- **Risk appetite**: total risk that the organization can bear in a given risk profile
  - Can be **conservative** (little tolerance), **expansionary** (high tolerance), or **neutral** (neither low nor high)

#### Risk Strategies

- **Accept**: acknowledge the risk but take no steps to address it; may include an **exception** (security requirement cannot be fully implemented) or an **exemption** (regulating body waives requirement)
- **Transfer**: shift risk to a third party (e.g., purchasing cybersecurity insurance; paying premiums so organization is compensated in event of attack)
- **Avoid**: identify the risk but decide not to engage in the activity
- **Mitigate**: address risk by making it less serious (e.g., repairing a vulnerability, erecting a fence)

#### Third-Party Risk Management

- **Third parties**: vendors, business partners, and supply chain members
- **Third-party risk management**: identifying third-party risks, assessing and selecting vendors, and using vendor agreement instruments
- Risks associated with third parties:
  - Coordination difficulties with diverse activities
  - Network access required for IT functions creates weakest-link vulnerability
  - **Supply chain infection**: attackers infiltrate organization through third-party vulnerability
- Third-party integration risks:
  - **On-boarding/off-boarding**: start-up and termination of partner relationships
  - Application and social media network sharing
  - Privacy and risk awareness
  - Data considerations (ownership, backup, unauthorized sharing)
- Vendor monitoring practices:
  - Annual questionnaires on supply-chain security
  - Regular penetration testing and **right-to-audit clause**
  - Evidence of internal audits and independent assessment
  - **Supply-chain analysis**: regular evaluations of supply chain steps
  - **Rules of engagement**: model defining expectations for how parties interact
  - **Due diligence**: reasonable steps to satisfy legal agreements
  - **Conflict of interests**: outside personal or financial interests that could impact agreement

#### Vendor Agreement Instruments

- **Service-level agreement (SLA)**: service contract specifying services, responsibilities, and guarantees
- **Business partnership agreement (BPA)**: contract establishing rules and responsibilities of business partners
- **Memorandum of understanding (MOU)**: describes agreement demonstrating "convergence of will"; generally not legally enforceable but more formal than unwritten agreement
- **Nondisclosure agreement (NDA)**: legal contract specifying how confidential material will be shared and restricted to others
- **Measurement system analysis (MSA)**: uses scientific tools to determine variation added to a process by a measurement system
- **Memorandum of agreement (MOA)**: establishes common legal terms creating a "conditional agreement" where transfer of funds for services is anticipated
- **Work order (WO) / Statement of work (SOW)**: document within a contract describing work requirements for a specific project along with performance and design expectations

#### Security Awareness Management

- **Security awareness management** (risk awareness): raising understanding to all employees of what risks exist, their potential impacts, and how they are managed
- **Anomalous behavior recognition**: distinguishing between what is normal and what is not normal
- **Situation awareness**: determining that which is unexpected, unintentional, and risky
- Learner traits by generation:
  - Pre-1946: patriotic, loyal, faith in institutions (75 million)
  - 1946–1964: idealistic, competitive, question authority (80 million)
  - 1965–1981: self-reliant, distrustful of institutions, adaptive to technology (46 million)
  - 1982–2000: pragmatic, globally concerned, computer literate, media savvy (76 million)
- Training approaches:
  - **Pedagogical approach**: "to lead a child"; students dependent on teacher; motivated by external pressures
  - **Andragogical approach**: "art of helping an adult learn"; self-directed; motivated by self-esteem and quality of life; triggered by perceived gap between current and desired state
- Learning styles: visual (notes, presentations), auditory (lectures, discussions), kinesthetic (labs, hands-on)
- Training techniques:
  - **Computer-based training (CBT)**: computer-delivered instruction; flexible (any location/time) with progress feedback
  - **Role-based awareness training**: specialized training customized to specific job role
  - **Gamification**: using game-based scenarios for instruction to heighten interest and retention
  - **Phishing simulations**: help employees recognize phishing attempts; tracks initial training to recurring training improvements
- Awareness program content should include:
  - Recognition of insider threats
  - Understanding of operational security
  - Social engineering attacks
  - Password management
  - Risks of removable media and cables
  - Security differences between office and hybrid/remote work
  - Security policies and handbooks
  - Environmental physical attacks

---

## Key Terms

- **accept**
- **ad hoc assessment**
- **adjusting dependencies**
- **Annualized Loss Expectancy (ALE)**
- **Annualized Rate of Occurrence (ARO)**
- **anomalous behavior recognition**
- **approval process**
- **asset**
- **asset acquisition**
- **asset assignment/accounting**
- **asset decommissioning**
- **asset disposal**
- **asset enumeration**
- **asset management**
- **asset procurement**
- **asset tracking**
- **avoid**
- **backout plan**
- **business partnership agreement (BPA)**
- **certification**
- **change management**
- **change management policies**
- **change management procedures**
- **changing allow lists/deny lists**
- **classification**
- **conflict of interests**
- **conservative**
- **continuous assessment**
- **convertibility/liquidity**
- **current asset**
- **Cybersecurity Asset Management (CAM)**
- **data retention**
- **degaussing**
- **destruction**
- **disposal**
- **due diligence**
- **E-bidding process**
- **evidence of internal audits**
- **exception**
- **exemption**
- **expansionary**
- **Exposure Factor (EF)**
- **experiencing downtime**
- **Failure in Time (FIT)**
- **fixed asset**
- **impact analysis**
- **implementing service or application restarts**
- **independent assessment**
- **initial training**
- **intangible asset**
- **inventory**
- **key risk indicators**
- **legacy systems**
- **likelihood**
- **maintenance window**
- **Mean Time Between Failure (MTBF)**
- **Mean Time to Failure (MTTF)**
- **Mean Time to Recovery (MTTR)**
- **measurement system analysis (MSA)**
- **memorandum of agreement (MOA)**
- **memorandum of understanding (MOU)**
- **micro-cut**
- **mitigate**
- **modifying restricted activities**
- **multiparty**
- **neutral**
- **nondisclosure agreement (NDA)**
- **nonoperating asset**
- **one-time assessment**
- **operating asset**
- **ownership**
- **phishing campaign**
- **probability**
- **purging**
- **qualitative risk analysis**
- **quantitative risk analysis**
- **questionnaires**
- **recurring assessment**
- **recurring training**
- **reporting and monitoring**
- **responding to reported suspicious messages**
- **right-to-audit clause**
- **Risk Control Self-Assessment (RCSA)**
- **risk**
- **risk appetite**
- **risk exposure factor**
- **risk identification**
- **risk impact**
- **risk matrix/heatmap**
- **risk owners**
- **risk probability**
- **risk register**
- **risk reporting**
- **risk threshold**
- **risk tolerance**
- **risky**
- **rules of engagement**
- **sanitization**
- **service-level agreement (SLA)**
- **Single Loss Expectancy (SLE)**
- **situation awareness**
- **software compliance and licensing**
- **Standard bidding process**
- **standard operating procedures**
- **stakeholders**
- **supply-chain analysis**
- **supply chain infection**
- **tangible asset**
- **test results**
- **third-party risk management**
- **transfer**
- **unexpected**
- **unintentional**
- **updating diagrams**
- **updating policies/procedures**
- **using legacy applications**
- **vendor monitoring**
- **version control**
- **vulnerability scanner**
- **wiping**
- **work order (WO)/statement of work (SOW)**

---

## Review Questions

1. Which of the following threats would be classified as the actions of a hacktivist?
   - a. External threat
   - b. Internal threat
   - c. Environmental threat
   - d. Compliance threat

2. Which of these is NOT a response to risk?
   - a. Mitigate
   - b. Accept
   - c. Resist
   - d. Avoid

3. Which of the following is NOT a threat classification category?
   - a. Compliance
   - b. Financial
   - c. Tactical
   - d. Strategic

4. In which of the following threat classifications would a power blackout be classified?
   - a. Operational
   - b. Managerial
   - c. Technical
   - d. Strategic

5. Which of the following approaches to risk calculation typically assigns a numeric value (1–10) or label (High, Medium, or Low) to represent a risk?
   - a. Quantitative
   - b. Qualitative
   - c. Rule based
   - d. Policy based

6. What is a list of potential threats and associated risks called?
   - a. Risk assessment
   - b. Risk matrix
   - c. Risk register
   - d. Risk portfolio

7. Giovanni is completing a report on risks. To which risk option would he classify the action that the organization has decided not to construct a new data center because it would be located in an earthquake zone?
   - a. Transfer
   - b. Avoid
   - c. Reject
   - d. Prevent

8. Aristide is explaining to a coworker the new cybersecurity asset management (CAM) system. Which of the following would he NOT say about a CAM?
   - a. It is a relatively new process that combines asset management with information security.
   - b. It can identify assets on a continuous and real-time basis.
   - c. It can use vulnerability scanners.
   - d. It is designed to replace asset management.

9. Emiliano needs to determine the expected monetary loss every time a risk occurs. Which formula will he use?
   - a. AV
   - b. SLE
   - c. ARO
   - d. ALE

10. Enzo is reviewing asset tracking for a certification exam. Which of the following is NOT true about asset tracking?
    - a. Asset tracking can be used to determine when assets should be upgraded, replaced, or disposed.
    - b. Asset tracking can help determine what assets add value.
    - c. Asset tracking is part of an asset management system.
    - d. Asset tracking traces the location of intangible assets.

11. Which of the following is a listing of assets by a seller of those assets?
    - a. Asset enumeration
    - b. Asset inventory
    - c. Asset counting
    - d. Asset verification

12. Which of the following is NOT a legally enforceable agreement but is still more formal than an unwritten agreement?
    - a. BPA
    - b. SLA
    - c. MOU
    - d. AMS

13. Angelo has received a document that is part of a contract that describes the work requirements for a specific project. What type of document is this?
    - a. EOA
    - b. BPP
    - c. SOW
    - d. EOS

14. Which of the following uses scientific tools to determine the amount of variation that is added to a process?
    - a. XRS
    - b. MSA
    - c. RAR
    - d. PDP

15. Which of the following risk management strategies utilizes cybersecurity insurance?
    - a. Accept
    - b. Transfer
    - c. Mitigate
    - d. Change

16. Which of the following is NOT a third-party risk?
    - a. On-boarding
    - b. Social media network sharing
    - c. Risk awareness
    - d. Network assignment

17. Sergio has been asked to provide historical data for calculating the likelihood of a risk. Which of the following data sets would he NOT submit?
    - a. Network packet analysis
    - b. Law enforcement data
    - c. Insurance company data
    - d. Data from computer incident monitoring organizations

18. Which of the following is used to minimize biases and prejudices regarding analyzing risks?
    - a. RCSA
    - b. RCA
    - c. SCRA
    - d. DOS

19. Which of the following is NOT a standard operating procedure that can impact information security?
    - a. Change in ownership or stakeholders
    - b. Implement impact analysis or test results
    - c. Execute backout plan or maintenance window
    - d. Change allow lists/deny lists

20. Gabe is creating a report for his supervisor Cora that outlines the total risk that the organization can bear in a given risk profile. Which of the following terms would Gabe be using?
    - a. Risk tolerance
    - b. Risk appetite
    - c. Risk expansion
    - d. Risk acceptance
