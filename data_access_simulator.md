# Data Access Decision Simulator – EduConnect Ghana

Author: *Nana Kwaku Sarpong*

## Introduction

EduConnect Ghana is an ed-tech platform serving over 50,000 students. As a DevOps engineer, you are responsible for ensuring that access to student data is granted according to the company’s **data classification policy**, **data lifecycle management principles**, and **compliance requirements under Ghana DPA**.  

The platform classifies data into three tiers:  

- **PUBLIC:** Marketing materials, public course catalogs  
- **INTERNAL:** Aggregated analytics, internal reports  
- **CONFIDENTIAL:** Student personally identifiable information (PII), grades, payment information  

The following scenarios simulate real data access requests that require careful decision-making to balance business needs, privacy, and security.


## Request 1: Marketing Campaign

**From:** Sarah Owusu, Marketing Manager  
**Request:** Access to full student database (names, emails, phone numbers, course enrollments) for referral campaign  
**Data Classification:**  
- Email addresses → CONFIDENTIAL  
- Names → INTERNAL  
- Enrollments → INTERNAL  
**Current Access Level:** INTERNAL

### Decision Form

**Decision:** Conditional Approval ✅  

**Lifecycle Stage:** Use / Share  

**Justification:**  
- Email addresses are **CONFIDENTIAL**, Sarah has only INTERNAL access.  
- Principle of least privilege: only minimum necessary data should be accessed.  
- Conditional approval protects PII while enabling marketing activities.

**Action Steps:**  
1. Provide **pseudonymized or hashed email addresses** or aggregated contact lists.  
2. Limit dataset to students eligible for referral campaigns.  
3. Log access and ensure deletion after campaign ends.  
4. Require **marketing manager signs a data usage agreement** specifying permitted use.  
5. Consult **Data Privacy Officer** and **Legal** before releasing CONFIDENTIAL data.  


## Request 2: Analytics Partnership

**From:** David Mensah, Head of Product  
**Request:** External partner (DataInsights Inc.) requires AWS DB access to analyze student learning patterns  
**Data Classification:**  
- Student activity logs → INTERNAL  
- Student profiles → CONFIDENTIAL  
**Compliance Note:** Ghana DPA applies

### Decision Form

**Decision:** Conditional Approval ⚠️  

**Lifecycle Stage:** Share / Use  

**Justification:**  
- Sharing CONFIDENTIAL student profiles externally requires compliance with Ghana’s DPA.  
- Principle of least privilege: third-party access must be limited to necessary datasets.  
- Cross-border data transfer triggers additional compliance requirements.

**Action Steps:**  
1. Only share **anonymized or aggregated student profiles**; exclude PII wherever possible.  
2. Implement **role-based access** and **temporary credentials** with audit logging.  
3. Establish **Data Processing Agreement (DPA)** with DataInsights Inc. specifying scope, retention, and security.  
4. Conduct **security and compliance review** prior to granting access.  
5. Maintain **documentation of approval, access logs, and dataset transformations**.  
6. Consult **Legal**, **Compliance**, and **Security** teams before final approval.


## Request 3: Archive & Deletion

**From:** Comfort Asante, Customer Support Lead  
**Request:** Delete student account (James Boateng) per "right to be forgotten"  
**Data Classification:** All student data → CONFIDENTIAL  
**Current Status:** Inactive, no outstanding obligations

### Decision Form

**Decision:** Approve ✅  

**Lifecycle Stage:** Destroy  

**Justification:**  
- Ghana DPA enforces the **right to erasure** when no obligations remain.  
- Student data is CONFIDENTIAL, deletion must be thorough and documented.  
- Principle of least privilege: only authorized personnel should execute deletion.

**Action Steps:**  
1. Remove all student data from active databases.  
2. Delete backups containing the student’s data, unless legally required.  
3. Update audit logs to record deletion request, execution date, and personnel involved.  
4. Confirm deletion with the student.  
5. Retain minimal **system metadata** for business continuity if permitted.  
6. Consult **Data Governance / Legal** if retention exceptions exist.


## Conclusion

This data access decision simulation demonstrates how EduConnect Ghana balances operational needs with data privacy, security, and compliance. By applying **data classification policies**, respecting the **principle of least privilege**, and adhering to **data lifecycle management** and **Ghana DPA requirements**, the platform ensures that sensitive student information is accessed, shared, and deleted responsibly.  

Each request highlights the importance of making informed, context-aware decisions to protect **CONFIDENTIAL data**, while still enabling business activities and collaborations. Proper documentation, consultation with legal and compliance teams, and controlled access mechanisms are critical to maintaining trust and regulatory compliance.
