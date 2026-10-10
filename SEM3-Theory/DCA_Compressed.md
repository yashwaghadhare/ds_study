# DCA (Data Compliance and Auditing): Complete Compressed Notes (Units 1 and 2)

> Exam-revision notes. Every question from the question bank (Q1 to Q36) is covered, merged by theme, in simple language.
> Q numbers in brackets (e.g., Q13) match the question bank. Several questions repeat in the bank (DPIA, consent, third-party, ePrivacy), so each topic is written **once** with all its Q numbers listed.
> Each unit ends with a **Last-Minute Cheat Sheet**.

## Contents
1. [Unit 1: Data Compliance (GDPR, ePrivacy, Third-Party Compliance)](#unit-1)
2. [Unit 2: Data Auditing (Security Audits, Threats, Social Engineering)](#unit-2)

---

<a id="unit-1"></a>
# UNIT 1: DATA COMPLIANCE (Q1 to Q18)

## BLOCK A: GDPR Basics
*(Q1, Q5, Q13)*

### Q1. GDPR and its importance
- **GDPR = General Data Protection Regulation.** A data protection **law of the European Union (EU)**, **applicable from 25 May 2018**. It controls how organisations **collect, store and use personal data** and gives people more control over their own information.
  - *General* = covers a wide range; *Data* = information about people; *Protection* = keeping it safe; *Regulation* = a law that must be followed.

**What GDPR requires organisations to do:**
1. **Process data lawfully, fairly and transparently** (legal reason, fair, open about what they do).
2. **Collect only necessary data** for a stated purpose.
3. **Keep data secure** (passwords, encryption).
4. **Respect people's rights:** access, rectification (correct wrong data), erasure (delete data).
5. **Report data breaches** to the authorities.
6. **Be accountable:** keep documentation to prove compliance.

**Why important:** strengthens privacy, improves security, builds trust, holds organisations accountable (heavy **fines**).
- *Example:* an online store with European customers must protect payment details, explain why it collects data, let customers see or delete their data, or face large fines.

### Q5. Material Scope of GDPR
- "Material scope" = **which types of processing and data GDPR covers** (answers "What activities does GDPR apply to?").

**What it covers:**
- The **processing of personal data** (any activity: collection, storage, use, sharing).
- **Personal data** = information about an **identified or identifiable natural person** (a living human who can be recognised, directly or indirectly).
- Processing by organisations **within the EU**, and **certain organisations outside the EU** (e.g., if they handle data of people in the EU).
- Considered in terms of **purpose (why)** and **means (how)**.

**Outside the scope:** specific legal exclusions (e.g., **purely personal or household activities**).

**Why understanding it matters:** decides whether GDPR applies; prevents **over-compliance** (wasted effort) and **under-compliance** (missed obligations).
- *Example:* storing customer names and emails = processing personal data → falls under GDPR if the customers are in the EU.

### Q13. Lawful Bases for Processing (the 6 lawful bases)
- **Lawful basis** = a valid **legal reason** for processing personal data. An organisation must have **at least one** before processing.

| # | Lawful basis | Meaning | Example |
|---|---|---|---|
| 1 | **Consent** | Person gave permission under valid conditions | Marketing emails |
| 2 | **Contract** | Necessary to carry out a contract with the person | Employee's bank details to pay salary; fulfilling an order |
| 3 | **Legal Obligation** | Required to comply with a law | Keeping tax records |
| 4 | **Vital Interests** | Necessary to **protect someone's life** (emergency) | Medical emergency |
| 5 | **Public Task** | Necessary for an **official public function** (usually government) | Government body duties |
| 6 | **Legitimate Interests** | Genuine business need, as long as it does **not unfairly harm** the individual | Business need with balance test |

- Organisations must **select and document** the basis for each activity; it must suit the purpose.
- **Do NOT assume consent is always required**: often another basis fits better.
- Processing **without** a valid basis is **illegal**.

---

## BLOCK B: Key GDPR Principles and Practices
*(Q2, Q7, Q6 + Q14)*

### Q2. Integrity and Confidentiality Principle
- A key **security principle** of GDPR with two parts:
  - **Integrity** = keeping data **accurate, complete and unchanged** (protected from wrongful alteration or damage).
  - **Confidentiality** = keeping data **secret and private** (no unauthorised access).

**How organisations achieve it:**
- **Access controls** (only the right people can open data)
- **Strong authentication** (strong passwords, two-step verification)
- **Encryption** (stored and in transit)
- **Audit logs** (who accessed or changed data)
- **Regular backups**
- **Security patches** (software updates)
- **Employee training**
- **Controlled sharing**

**Why important:** poor integrity = wrong records and wrong decisions; poor confidentiality = identity theft, fraud, loss of trust.
- *Example:* a college database of marks: only authorised staff can modify marks (integrity); passwords, role-based access, encryption and audit logs protect privacy (confidentiality).

### Q7. Data Protection by Design and by Default
Privacy must be **built into systems**, not added as an afterthought.

| | **By Design** | **By Default** |
|---|---|---|
| Meaning | Privacy considered **from the very beginning** (during planning and building) | The **most privacy-friendly settings are ON automatically** (no user action needed) |
| Includes | Identify privacy risks at planning stage; build in technical and organisational safeguards | Collect only necessary data; limit access to authorised users; control retention; encryption from the start |
| Analogy | Planning **fire exits while designing** a building | Safe settings already switched on |

- **Why important:** reduces privacy risks early; makes privacy built-in; cheaper and safer than fixing later.
- *Example:* a student portal collects only enrollment data, uses encryption from the start (design), and default profile settings prevent public disclosure while role-based access limits teachers (default).

### Q6 + Q14. Consent Management
- **Consent** = permission. Under GDPR it is one lawful basis. **Consent management** = the proper way to **obtain, record, maintain and allow withdrawal** of consent.

**Valid consent must be:**
1. **Freely given:** a genuine free choice, not forced.
2. **Specific:** for a clear purpose, not "agree to everything".
3. **Informed:** clear information before agreeing.
4. **Unambiguous:** a **clear positive action**; **pre-ticked boxes are NOT valid**; silence is not consent.
5. **Clearly separated:** kept **separate** from other matters.

**What organisations must also do:**
- **Keep evidence** (when and how consent was obtained).
- **Allow easy withdrawal** at any time, **as easy as giving it**.
- **Review regularly**; consent is not permanent.
- Make **purpose and scope identifiable**.

**Why important:** transparency, user control, proof for the organisation.
- *Example:* a separate, unticked checkbox for marketing emails; the choice is stored with date and purpose; an easy "unsubscribe" page for withdrawal.

---

## BLOCK C: Assessments, Roles and Compliance Structure
*(Q3 + Q9, Q8, Q10, Q11)*

### Q3 + Q9. Data Protection Impact Assessment (DPIA)
- **DPIA** = a structured check of the **privacy risks of a new activity BEFORE it begins**, especially when there may be **high risk** to people's privacy. Aim: find and reduce risks early.

**Purpose (what it does):**
1. **Describes the processing** (nature, purpose, scope: what data, why, how much).
2. **Checks necessity and proportionality** (is it really needed? not excessive?).
3. **Identifies risks** to individuals (unauthorised access, misuse, leakage).
4. **Assesses likelihood and severity** of each risk.
5. **Plans safeguards/measures** (access controls, encryption, data minimisation, retention limits) and documents them.

**Why important:** finds risks **before** processing (preventive); supports **accountability**; helps responsible decisions; should be **reviewed again** if the activity changes significantly.
- *Example:* a company planning a **biometric attendance system** (fingerprints/face scans) or a hospital planning a **patient monitoring system** does a DPIA first, then sets controls (restricted access, encryption, limited retention).

### Q8. Data Protection Officer (DPO)
- A specially appointed person who **supports and guides** the organisation in managing data protection (the organisation's data protection expert and advisor).

**Responsibilities:**
- **Provide advice** on data protection obligations.
- **Monitor compliance** with policies.
- **Advise on DPIAs.**
- **Guide on risks and safeguards.**
- **Support training and awareness.**
- **Monitor audits.**
- **Cooperate with supervisory authorities** (contact point).
- **Handle contact from individuals** about data protection matters.

**Qualities required:** **appropriate expertise** and **independence** (to raise concerns without pressure).
**Why important:** governance, accountability, systematic data protection.
- *Example:* DPO reviews a new customer database and advises on lawful processing and security; helps monitor data subject requests.

### Q10. Role of GDPR in Compliance and Auditing
- **Compliance** = following the rules. **Auditing** = officially checking whether rules are followed.

**GDPR's role in compliance:** sets **principles and obligations**; encourages **accountability** (prove responsibility, not just claim it).

**GDPR's role in auditing:** GDPR requirements act as the **audit criteria** (the standard). An audit reviews:
- **Lawful bases**, **Transparency**, **Data rights** (access, correction, deletion), **Security** (access controls), **Documentation** (records of processing), **Data subject requests**, **Breach management**, **Retention and deletion**.

**How auditing leads to improvement:** findings identify **gaps** → **corrective actions** → **follow-up reviews** check the fix → ongoing cycle.
- *Example:* an audit finds too many people have database access → access is restricted → follow-up audit confirms it.

### Q11. Three Layers of Operational Data Protection ("three lines of defence")
- **Operational data protection** = putting data protection into practice in **daily work**.

| Layer | Name | Job | College example |
|---|---|---|---|
| **Layer 1** | **Operational (Business) layer** | People who **handle data daily**, apply policies, **own and manage the risks** in daily activities | Staff entering marks and updating records |
| **Layer 2** | **Control (Oversight) layer** | **Monitors compliance**, manages risk, reviews controls, supports Layer 1 with guidance and **challenge** | Compliance or management function |
| **Layer 3** | **Independent Assurance (Audit) layer** | **Independently evaluates** whether governance and controls actually work; gives **independent assurance** | Internal audit function |

- **Why three layers:** clear responsibilities, each layer checks in a different way, stronger protection and accountability.

---

## BLOCK D: ePrivacy
*(Q4, Q12, Q16, Q18)*

### Q4 + Q16 + Q18. ePrivacy and regulation of electronic communications
- **ePrivacy** = "e" for **electronic** + privacy. A **European law** protecting the **privacy and confidentiality of electronic communications** (phone calls, emails, text messages, internet browsing). **GDPR covers all personal data broadly; ePrivacy zooms in on electronic communications.**

**How it regulates communications:**
1. **Protects confidentiality** of communications (no improper listening, reading, interference).
2. **Covers device storage and access:** rules for **cookies** and similar tracking technologies on user devices.
3. **Sets duties for providers** (phone and internet companies must protect confidentiality).
4. **Prevents intrusive practices.**
5. **Regulates direct electronic marketing** (promotional emails and texts).
6. **Requires consent** (or other permitted conditions) where needed, e.g., non-essential cookies and certain marketing.
7. **Requires clear information** to users.
8. **Requires security** measures against unauthorised access.
9. **Maintain records** where consent is the basis.

- **Covers:** communication **content** and **related information (metadata)**.
- **Works with GDPR:** ePrivacy **complements** GDPR (together = complete privacy protection).
- **Why important:** keeps communications private, controls unwanted marketing and tracking, builds trust.
- *Example:* a company sending promotional emails must follow marketing rules, use appropriate consent, keep consent records, and protect message contents.

### Q12. ePrivacy, cookies and tracking technologies
- **Cookie** = a small text file a website stores on your device to remember information (login, browsing habits). **Tracking technologies** follow what you do online.

**ePrivacy rules:**
- **Protects information on your device** from access without permission.
- **Non-essential cookies (advertising, analytics) need consent first.**
- **Necessary cookies** (e.g., keep you logged in) may **not need consent**.
- **Requires clear information** about tracking.
- **Consent must be meaningful and real** (not hidden, tricky or misleading).
- Gives users a **real choice to accept or reject** optional tracking.

| Cookie type | Consent needed? | Example |
|---|---|---|
| **Necessary / essential** | Usually **no** | Session cookie keeping you logged in |
| **Advertising trackers** | **Yes** | Builds a marketing profile |
| **Analytics trackers** | Usually **yes** | Studies behaviour on the site |

- *Example:* a shopping site uses a session cookie (necessary) and wants an advertising tracker (optional) → needs a **cookie banner** so the user can accept or reject it.

---

## BLOCK E: Third-Party Compliance
*(Q15, Q17)*

### Q15 + Q17. Third-Party Compliance Standard
- **Third party** = an **outside company** the organisation works with (vendor, **data processor**, service provider). **Third-party compliance** = managing the **privacy and security risks** that come from these external parties. The **standard** = the set of rules and controls used.
- **Why a concern:** third parties create **privacy, security, operational and compliance risks**; their weakness becomes your risk, and the original organisation is **often still held responsible** for a leak.

**Controls in the standard:**
1. **Identify vendors** that access sensitive or personal data.
2. **Evaluate before granting access** (due diligence **before onboarding**: security policies, access controls, encryption, incident response, certifications, past incidents).
3. **Use clear contracts** defining responsibilities and data-processing requirements.
4. **Include security and privacy requirements** in agreements.
5. **Give minimum necessary access** (**least privilege**).
6. **Define incident notification** (third party must report breaches quickly).
7. **Monitor performance** throughout (regular reviews and audits; **periodic assessments**).
8. **Specify retention and deletion**; at contract end, data is **returned or securely deleted**.

- **Importance:** reduces supply-chain risk, protects data in transit to and from third parties, supports overall compliance.
- *Example:* a college using a cloud service for student records, or a company outsourcing payroll: assesses the provider first, contract specifies permitted use, security, confidentiality, breach reporting, audit rights; data deleted when contract ends.

---

## Unit 1: Last-Minute Cheat Sheet
- **GDPR** = EU law, applicable **25 May 2018**; controls collection, storage, use of personal data; heavy fines.
- **Obligations:** lawful, fair, transparent; collect only necessary data; secure data; respect rights (access, rectification, erasure); report breaches; be accountable.
- **Material scope:** processing of **personal data of identifiable living people**; some outside-EU organisations too; **household activities excluded**.
- **6 lawful bases:** Consent, Contract, Legal Obligation, Vital Interests, Public Task, Legitimate Interests. **Don't assume consent always.**
- **Integrity** = accurate and unchanged. **Confidentiality** = secret and private. Tools: access control, authentication, encryption, audit logs, backups, patches, training.
- **By Design** = privacy built in from the start. **By Default** = most private settings on automatically.
- **Valid consent:** freely given, specific, informed, unambiguous (**no pre-ticked boxes**), separated; keep evidence; **easy withdrawal**.
- **DPIA** = risk check **before** a high-risk activity (describe → necessity and proportionality → risks → likelihood and severity → measures).
- **DPO** = adviser: advises, monitors compliance, advises on DPIAs, trains, cooperates with authorities; needs **expertise and independence**.
- **Three layers:** Operational → Control/Oversight → Independent Audit.
- **ePrivacy** = privacy of electronic communications; **cookies**: necessary (no consent) vs advertising/analytics (consent); regulates direct marketing; **complements GDPR**.
- **Third-party compliance:** due diligence before onboarding, contracts, least privilege, incident reporting, monitoring, secure deletion at the end.

---

<a id="unit-2"></a>
# UNIT 2: DATA AUDITING (Q19 to Q36)

## BLOCK A: Audit Planning, Process and Documents
*(Q24, Q25, Q29, Q23, Q32, Q28)*

### Q24. Pre-Audit Checklist
- A list of tasks completed **BEFORE** a security or compliance audit starts, so the audit runs smoothly (like a pilot's checklist before a flight).

**Major points:**
1. **Identify audit scope and objectives** (what will be covered, what it aims to achieve).
2. **List relevant systems and departments** (systems, applications, locations).
3. **Identify applicable requirements** (policies, standards, legal requirements).
4. **Review asset inventories** for completeness.
5. **Make risk assessments and risk registers available.**
6. **Collect security policies and procedures.**
7. **Check previous audit findings** and confirm corrective actions were done.
8. **Prepare access-control records** (access lists, user management).
9. **Gather key records:** incident, backup, vulnerability, security-monitoring records.
10. **Identify document owners** (so evidence can be provided quickly).

- **Why important:** reduces delays, ensures evidence isn't missed, improves audit readiness.
- *Example:* before a network audit: verify network diagrams and asset inventory, prepare firewall rules, vulnerability reports, access records, incident logs.

### Q25. Information Gathering (a phase of a security audit)
- An **early phase** where auditors **collect facts and details** to understand the organisation and systems **before deeper testing** ("you cannot check something until you understand it").

**What auditors gather:**
- **Key elements:** assets, applications, networks, users, **data flows**.
- **Network diagrams and system documentation.**
- **Asset inventories.**
- **Public information** (when appropriate).
- **Interviews** with staff (processes and responsibilities).
- **Configuration and policy documents** (existing controls).

**Key points:** accuracy matters (incomplete information leads to wrong conclusions); it supports later **risk and vulnerability analysis**; must stay **within the authorised audit scope**.
- *Example:* auditor compares the asset inventory with systems actually found; **unexpected assets** (not on the official list) may indicate documentation or governance gaps.

### Q29. External Security Audit
- A security check done by an **independent party from OUTSIDE** the organisation (not its own staff), giving an **objective, unbiased** assessment.

**How it works:** define scope → review policies, processes, systems, technical controls within scope → examine key areas (access control, network security, vulnerability management, incident response) → document findings with **risk ratings and recommendations**.

**Objectives:**
- Provide an **objective assessment** of security controls.
- Identify weaknesses **internal teams may overlook** (too close to the work).
- Provide **evidence** of control effectiveness.
- Help management **prioritise corrective actions.**
- Support **contractual or compliance requirements.**
- **Value:** independent assurance, catches what insiders miss, improves governance.
- *Example:* an outside auditor reviews firewall configuration, authentication, patching, monitoring; final report with observations, risks, recommendations; follow-up verifies fixes.

### Q23. Risk Assessment Reports and Risk Registers
- **Risk assessment** = identifies and evaluates risks. **Risk assessment report** = documents the findings and conclusions. **Risk register** = a **structured list (table) of all identified risks**.

**A risk register records:** **Risk description**, **Likelihood**, **Impact**, **Owner** (person responsible), **Treatment** (plan to deal with it).

**Role in security auditing:**
- Auditors **understand the risk profile.**
- **Compare documented risks with actual conditions** observed.
- **Prioritise remediation** (which to fix first).
- **Assign responsibility** (risk owners).
- **Communicate significant risks to management.**
- **Record residual risks.**
- Support audit planning, accountability, continuous improvement; follow-up audits verify treatments were completed.
- *Example:* unauthorised access found as high risk → register records asset, owner, existing controls, treatment plan → management informed → follow-up audit verifies.

### Q32. Residual Risk and Risk Acceptance

| | **Residual Risk** | **Risk Acceptance** |
|---|---|---|
| Meaning | The risk that **REMAINS after controls** are implemented (no control removes every risk) | A **conscious decision to live with a risk** instead of adding more controls |
| When | Always some risk stays | When the remaining risk is **within approved tolerance** |
| Requirements | Assess remaining **likelihood and impact**; **monitor** (circumstances change) | Must be **informed and documented** (not ignoring); **risk owner** understands consequences; consider controls first |

- Acceptance **does NOT mean the risk has disappeared**.
- The decision is recorded in the **risk register with an owner and a review date**; if the risk increases later, **more treatment** may be needed.
- *Example:* multi-factor authentication reduces account compromise risk, but some risk remains (lost devices, other attacks) → residual risk → management accepts it within tolerance → recorded with owner and review date.

### Q28. Transparency and Fairness Standard
- **Transparency** = being **open and clear** about data processing (like clear glass). **Fairness** = processing in a way that **respects individuals** and avoids unjustified harmful effects. Together: be **honest and clear** about data use and **treat people fairly**.

**Requirements:**
- **Tell people what data is collected and why.**
- Use **simple, appropriate language** (no confusing legal jargon).
- **Do not mislead** (purposes not hidden).
- **Avoid collecting unnecessary** data for unrelated purposes.
- **Give access to rights information.**
- **Stay consistent** with stated purposes and expectations.
- **Review notices** when processing changes.
- **Why important:** builds trust, supports accountable processing, essential in a strong compliance framework.
- *Example:* an online college form explains in simple language why contact information is collected, how it is used and who receives it, and does **not** secretly use it for unrelated marketing.

---

## BLOCK B: Threats, Vulnerabilities and Risk Management
*(Q19, Q31, Q21 + Q26)*

### Q19. Threats vs Vulnerabilities

| | **Threat** | **Vulnerability** |
|---|---|---|
| Meaning | A **potential cause of harm**: the danger itself | A **weakness** that can be exploited |
| Role | The **SOURCE** of possible harm | Provides the **OPPORTUNITY** for harm |
| Sources / places | Hackers, malware, insiders, accidents, natural events (fire, flood) | Software, hardware, configurations, processes, **people** |
| Examples | Phishing attacker, virus | Unlocked door, **outdated/unpatched software**, employee who can't spot phishing |

- **Relationship:** **harm happens only when a threat meets a vulnerability**; risk increases when a threat can exploit an important vulnerability.
- **Link to audits:** audits **identify vulnerabilities** so they can be fixed; controls are chosen to reduce likelihood or impact.

### Q31. Threat Management
- The **ongoing process of identifying, assessing, monitoring and responding to threats**, to defend against the sources of cyber attacks.

**How it works:**
1. **Gather threat information** (monitoring, vulnerability analysis, past incidents, intelligence).
2. **Identify exposed assets.**
3. **Prioritise by risk** (most significant threats first).
4. **Apply controls** (firewalls, endpoint protection, authentication, monitoring).
5. **Investigate and respond** to incidents.
6. **Keep it continuous** (threats keep changing).
7. **Learn from incidents** to improve controls.

- **Importance:** reduces likelihood and impact of attacks; **proactive** risk management.
- *Example:* repeated phishing attempts → strengthen awareness training and email filtering, monitor and report suspicious messages, patch related vulnerabilities, track trends.

### Q21 + Q26. Vulnerability Analysis
- The **systematic study to identify weaknesses** in systems, applications, networks and configurations. Covers operating systems, applications, networks, configurations.

**Process:**
1. **Asset discovery and scanning** (find all systems, run security scans).
2. **Analyse weaknesses** (possible impact).
3. **Classify by severity and exploitability.**
4. **Compare with security baselines** (approved standards).
5. **Technical testing** (missing patches, insecure configurations).
6. **Application testing** (injection flaws like SQL injection).
7. **Validate findings** to reduce **false positives** (false alarms).
8. **Evaluate likelihood and impact.**
9. **Document in a structured vulnerability report** (record affected assets and recommended corrective actions).
10. **Prioritise remediation** (critical first).

- **Methods:** **automated scanning** (finds known weaknesses quickly) + **manual review** (finds configuration and process issues tools miss).
- **Why important:** reduces the **attack surface**; provides evidence for risk-based improvement; fixes weaknesses before attackers exploit them; **trend analysis** shows whether security is improving.
- *Example:* scan finds an outdated server component → patch it → follow-up scan verifies the weakness is gone.

---

## BLOCK C: Social Engineering
*(Q20, Q34, Q22)*

### Q20 + Q34. Human-based vs Computer-based Social Engineering
- **Social engineering** = **tricking and manipulating people** (not hacking computers) into revealing secrets or doing something harmful. It exploits **trust, fear, urgency, curiosity, authority**.

| | **Human-based** | **Computer-based** |
|---|---|---|
| Meaning | Trick done **directly by a person** targeting people | Trick done **using digital systems** (computers, emails, websites) |
| Reach | One person at a time | **Many people at once, cheaply** |

**Common techniques (Q20 human-based):**
- **Phishing:** fake messages or websites to steal information.
- **Pretexting:** a **made-up story** to get information.
- **Impersonation:** pretending to be a boss, IT staff, or a bank.
- **Baiting:** attractive offer or object (free gift, **infected USB**).
- **Tailgating:** following an authorised person into a restricted area.
- **Shoulder surfing:** watching someone type a password.
- **Vishing:** **voice** calls (v = voice).
- **Smishing:** **SMS** text messages (sm = SMS).

**Common techniques (Q34 computer-based):** **phishing emails**, **smishing**, **vishing**, **fake websites** imitating real services, **malicious attachments** (disguised as invoices), **fake pop-up messages** claiming a security problem, **urgency and authority tricks**.

**Defences:** **security awareness training** (verify unusual requests via official channels, check sender and website address); **phishing simulations**; **multi-factor authentication** (stolen password alone isn't enough); **email filtering and endpoint security**. Needs **people + process + technical controls** together.
- *Example (human):* attacker calls pretending to be IT (impersonation) with an urgent story (pretexting) asking for a password.
- *Example (computer):* fake banking email leads to a counterfeit login page that captures credentials.

### Q22. Phishing Simulations in security audits
- A **controlled test** where the organisation sends **fake but harmless phishing messages to its own employees** to check how they respond (realistic, **without actual harm**).

**Role in audits:**
- **Measures employee awareness.**
- **Tests specific behaviours** (click links? open attachments? report the message?).
- **Identifies training needs.**
- **Provides metrics:** **reporting rate** (how many reported) and **interaction rate** (how many fell for it).
- **Shows improvement over time** through repeated simulations.

**Done properly:** **authorised** and ethically designed; don't collect sensitive information unnecessarily; give **educational guidance, not punishment**.
- **Value:** practical evidence of human risk; complements technical controls; turns mistakes into learning.
- *Example:* a fake password-reset email: those who report it (good), those who click get immediate guidance; aggregated results show awareness gaps.

---

## BLOCK D: Technical and Network Audits
*(Q33, Q30, Q35, Q36)*

### Q33. Firewall Security Audit
- A **firewall** controls traffic in and out of a network (security guard: allows safe traffic, blocks dangerous). A **firewall security audit** checks that it is **configured and operating effectively**.

**Major activities:**
1. **Define scope** (firewall systems and review scope).
2. **Examine architecture** and network diagrams.
3. **Review rule sets** for **unnecessary, duplicate or overly broad** rules.
4. **Check rule values** (source, destination, service, action) match business needs.
5. **Remove unused rules** and obsolete objects (old rules create gaps).
6. **Restrict and monitor administrative access.**
7. **Review logs** (enabled and reviewed).
8. **Check configuration backups and change-management.**
9. **Keep firmware and software up to date.**

- **Importance:** reduces **misconfiguration** and unauthorised network access risks; key to network security assurance.
- *Example:* a rule allowing unrestricted access to a sensitive server is narrowed to approved sources and required services; change documented and tested.

### Q30. IDS Security Auditing
- **IDS = Intrusion Detection System:** a tool that **monitors activity for suspicious or malicious behaviour** (like a security alarm). **IDS auditing** = checking that it is **properly configured and working effectively**.

**What IDS auditing examines:**
- **Detection rules and settings**, alert settings, log collection.
- **Coverage** of important events (are they actually monitored?).
- **Alert handling procedures** (who investigates and responds).
- **Log protection** (against unauthorised modification).
- **Up-to-date detection** of current threats.
- **False positives** (false alarms) and **false negatives** (missed real attacks).
- **Alert delivery** (alerts actually reach security personnel).

- **Importance:** strengthens visibility into suspicious activity, supports **timely detection**, keeps monitoring relevant as systems change.
- *Example:* check that repeated unauthorised login attempts generate IDS alerts that are logged and investigated; if the IDS fails to alert, it is a serious problem to fix.

### Q35. Internal Network Security Audit
- Evaluates security **WITHIN** the internal network: what damage someone **already inside** (dishonest employee, hacker who got in) could do.

**What it examines:**
- **Network architecture, configuration, access controls.**
- **Network diagrams and segmentation** (dividing the network into zones).
- **Unnecessary exposure** of internal services.
- **Access restrictions** (users reach only needed resources).
- **Internal vulnerabilities** (scanning internal hosts).
- **Firewall and router settings.**
- **Wireless (Wi-Fi) security.**
- **Logging and monitoring.**

- **Importance:** prevents unauthorised **lateral access** (moving sideways through the network), reduces attack surface, catches internal weaknesses; findings prioritised by risk.
- *Example:* a student computer network can directly access an administrative database → fixed with **network segmentation** and firewall rules.

### Q36. SQL Injection and XSS (web application vulnerabilities)
- **Web application** = website or online app (banking, shopping), a common attack target.

| | **SQL Injection** | **XSS (Cross-Site Scripting)** |
|---|---|---|
| What | **Untrusted input** (typed by a user) is unsafely included in **database queries**, letting an attacker insert harmful commands | **Untrusted content runs as a script** in a user's browser (attacker sneaks harmful code into a page; it runs for anyone who views it) |
| Impact | **Unauthorised data access or modification** | Affects **users viewing** the vulnerable page |
| Prevention | **Parameterized queries** + **input validation** | **Output encoding** + content security controls; input handling suited to context |
| Example | Special characters typed in a login box trick the database into granting access without a valid password | A comment field shows an attacker's script to other visitors; harmful code runs in their browsers |

- **Both:** affect confidentiality, integrity and user trust; very common; prevented by **secure coding, security testing and regular vulnerability assessments**.

---

## BLOCK E: Physical Security
*(Q27)*

### Q27. Secure Storage of Physical Documents
- **Physical documents** = real paper records (printed files and forms). They must be stored safely because they can be **seen, stolen or damaged**.

**How to store securely:**
- Use **secure locations** (secure rooms, locked cabinets).
- **Limit access** to authorised personnel.
- **Control keys and access cards.**
- **Organise** so sensitive records aren't unnecessarily exposed.
- **Define retention periods.**
- **Destroy securely** (**shredding**, not just a bin).
- **Protect from environmental damage** (fire, water).
- **Keep access records** for highly sensitive material.

**Extra precautions:** **clear desk policy** (no copies left on desks or public areas); protect documents **during transport**; **regular checks** that controls still work.
- **Why important:** supports **confidentiality, integrity, availability** and compliance with data protection rules.
- *Example:* employee files in a locked cabinet for authorised HR staff only; old files shredded.

---

## Unit 2: Last-Minute Cheat Sheet
- **Threat** = source of harm (hacker, virus). **Vulnerability** = weakness (unpatched server, untrained employee). Harm happens when a threat exploits a vulnerability.
- **Pre-audit checklist:** scope and objectives, systems, requirements, asset inventories, risk registers, policies, previous findings, access records, key records, document owners.
- **Information gathering:** early audit phase; assets, diagrams, inventories, interviews, configuration/policy documents; stay in scope.
- **External audit** = independent outsider; objective; finds what insiders miss; supports compliance.
- **Risk register fields:** description, likelihood, impact, owner, treatment. **Residual risk** = remaining after controls. **Risk acceptance** = informed, documented, within tolerance, with owner and review date.
- **Threat management:** gather intelligence → identify exposed assets → prioritise → apply controls → respond → continuous → learn.
- **Vulnerability analysis:** scan + manual review, classify severity, validate (reduce false positives), report, prioritise remediation, trend analysis.
- **Human-based SE:** phishing, pretexting, impersonation, baiting, tailgating, shoulder surfing, vishing (voice), smishing (SMS). **Computer-based SE:** phishing emails, fake websites, malicious attachments, fake pop-ups.
- **Defence:** awareness training, MFA, email filtering, phishing simulations (metrics: reporting rate, interaction rate; educate, don't punish).
- **Firewall audit:** rules (unnecessary, duplicate, broad), unused rules, admin access, logs, backups, change management, firmware.
- **IDS audit:** rules, coverage, alert handling, log protection, up-to-date, false positives/negatives, alert delivery.
- **Internal network audit:** segmentation, lateral access, exposure, Wi-Fi, monitoring.
- **SQL Injection** → parameterized queries and input validation. **XSS** → output encoding.
- **Physical storage:** locked cabinets, limited access, key control, shredding, clear desk, protect from fire and water.
- **Transparency and fairness:** tell people what and why, simple language, no misleading, no unnecessary collection.

---

*End of notes. Best of luck for the exam!*
