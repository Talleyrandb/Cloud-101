# Data protection 

## What is Data protection 

It refers to the set of laws, regulations, and practices designed to safeguard personal information collected, stored, and processed by organizations. This concept is fundamentally rooted in the recognition of individuals' rights regarding their personal data, which includes the ability to know what information is held about them, the right to update or correct inaccuracies, and the right to control how their data is used.
It is crucial to distinguish between various categories of information based on their sensitivity and intended use.

## Public Information 
Refers to data that is freely available to the general public. This information can be accessed without any restrictions and is typically disseminated through official channels such as government publications, websites, or press releases. Examples include:

*  Government reports
*  Public records (e.g., birth and death certificates)
*  Academic research that has been published openly

The key characteristic of Public Information is that it does not require special permissions for access, and its disclosure does not pose any risk to individuals or organizations.

## Internal use only
is information that is intended for internal use within an organization. This type of information is not meant to be shared with the public and typically includes operational data, internal policies, and employee communications. Examples include:

*  Internal memos
*  Strategic plans
*  Financial reports that are not publicly disclosed

The primary purpose of Internal use Only is to facilitate the smooth functioning of the organization while maintaining confidentiality among employees.

## Confidential 
Encompasses sensitive information that is protected from unauthorized access and disclosure. This type of information can include trade secrets, proprietary data, and personal information about clients or employees. Examples include:

*  Customer lists
*  Product designs
*  Financial data subject to privacy regulations

Organizations implement strict controls to safeguard Confidential Information, often requiring non-disclosure agreements (NDAs) to ensure that employees and partners do not share this information without permission.

## Restricted 
Refers to data that has limited access due to its sensitive nature. This category may overlap with Confidential Information, but it specifically implies that access is restricted based on specific criteria, such as security clearance levels or regulatory requirements. Examples include:

*  Classified government documents
*  Sensitive health information protected under laws like HIPAA
*  Corporate financial statements prior to public release

Access to Restricted Information is typically controlled through formal processes, ensuring that only authorized individuals can view or handle the information.

##Personally Identifiable Information (PII) 
Refers to any information that can be used to identify a specific individual. This category of information is crucial in various contexts, including data protection, privacy laws, and cybersecurity.

## Types of PII
Direct Identifiers; These are pieces of information that can uniquely identify an individual without the need for additional data. Examples include:

Identifiers:
*  Social Security Number (SSN): A unique number assigned to individuals for identification purposes in the U.S.
*  Driver’s License Number: Used for identification and verification in various contexts.
*  Passport Number: Essential for international travel and identification.

Biometric Data:
*  Fingerprints: Unique to each individual and used for security and identification.
*  Facial Recognition Data: Used in security systems and for identity verification.
*  Iris Scans: Another form of biometric identification that is highly secure.

Financial Information:
*  Bank Account Numbers: Critical for accessing financial resources.
*  Credit Card Numbers: Used for transactions and can lead to financial fraud if compromised.

Medical Records:
*  Health Insurance Information: Includes details about an individual's health coverage.
*  Medical Histories: Sensitive information regarding an individual's health conditions and treatments.

Personal Data:
*  Full Name: Can be used to identify an individual when combined with other data.
*  Address Information: Includes home addresses, which can be used for identity theft or stalking.

Legal Information:
*  Criminal Records: Sensitive data that can affect employment and personal reputation.
*  Court Records: Details about legal proceedings that may be harmful if disclosed without consent.


Quasi-Identifiers: These are data points that, when combined with other information, can lead to the identification of an individual. Examples include:

*  Date of Birth
*  Gender
*  Geographic Location
*  Race

## Categories of PII
PII can be categorized into two main types based on sensitivity:
## Sensitive PII: 
This includes information that could lead to significant harm if disclosed, such as financial records, medical history, and biometric data.
## Non-Sensitive PII: 
This includes information that is generally available from public sources and poses less risk if exposed, such as ZIP codes or gender.

# PCI for Data Privacy and Protection
The Payment Card Industry Data Security Standard (PCI DSS) is a set of security standards designed to ensure that all companies that accept, process, store, or transmit credit card information maintain a secure environment. This standard was developed to protect cardholder data from theft and fraud, addressing the increasing prevalence of data breaches in the financial sector.
## Key Characteristics of PCI DSS
Scope of Protection: PCI DSS applies to all entities involved in payment card processing, including merchants, service providers, and financial institutions. It encompasses various forms of sensitive data, including:
Sensitive Data Types Under PCI DSS

Cardholder Data (CHD):
*  Primary Account Number (PAN): The unique number identifying the cardholder's account, typically found on the front of the card.
*  Cardholder Name: The name of the individual to whom the card is issued.
*  Expiration Date: The date when the card is no longer valid.
*  Service Code: A three or four-digit code on the magnetic stripe used for transaction authentication.

  Sensitive Authentication Data (SAD):
*  Full Magnetic Stripe Data: This includes all data stored on the magnetic stripe or chip, which is used during transactions.
*  Card Verification Codes: Such as CVV, CVC, CID, which are security codes printed on cards.
*  PINs and PIN Blocks: Personal Identification Numbers used for authenticating transactions.

## Compliance Requirements: 
Organizations must adhere to 12 core requirements that are grouped into six goals:
- 1. Build and maintain a secure network and systems: This includes installing firewalls and not using vendor-supplied default passwords.
- 2. Protect cardholder data: Organizations must encrypt stored data and protect it during transmission.
- 3. Maintain a vulnerability management program: Regular updates and security patches are necessary.
- 4. Implement strong access control measures: Access to cardholder data should be restricted based on business needs.
- 5. Regularly monitor and test networks: This involves tracking all access to network resources and conducting regular security testing.
- 6. Maintain an information security policy: Organizations should have a comprehensive policy that addresses security measures.
##Technologies Used in PCI Compliance
To achieve compliance with PCI DSS, organizations utilize various technologies and practices:
- Firewalls: Essential for creating a barrier between secure internal networks and untrusted external networks.
- Encryption: Used for protecting cardholder data during transmission over public networks.
- Tokenization: Replaces sensitive card information with non-sensitive equivalents (tokens) that cannot be reversed without the original data.
- Access Control Systems: Ensure that only authorized personnel can access sensitive data Examples of PCI Data
### Examples of data protected under PCI DSS include:
Cardholder Data:
- Full credit card number (Primary Account Number or PAN)
- Cardholder name
- Expiration date
- CVV/CVC codes
Sensitive Authentication Data:
- PINs used for card transactions
- Magnetic stripe data
## Importance of PCI Compliance
- Fraud Prevention: By adhering to PCI DSS, organizations reduce the risk of data breaches and fraud, which can lead to significant financial losses.
- Legal Compliance: Non-compliance can result in hefty fines, legal repercussions, and damage to reputation.
- Customer Trust: Demonstrating commitment to data protection fosters trust among customers, which is crucial for maintaining business relationships

# References: 
[Data falls under PCI](https://blog.rsisecurity.com/what-data-falls-under-pci-compliance/)
[What is PCI DSS](https://www.techtarget.com/searchsecurity/definition/PCI-DSS-Payment-Card-Industry-Data-Security-Standard)
[PCI Security Standards](https://www.pcisecuritystandards.org/standards/)
[title](https://www.strikegraph.com/blog/pci-dss-policy)
[title](https://sprinto.com/blog/pci-dss-controls/)
[title](https://pcicompliancehub.com/the-12-requirements-of-pci-dss-v4-0-explained/)
[title](https://contractbook.com/dictionary/confidential-information)
[title](https://docs-prv.pcisecuritystandards.org/Guidance%20Document/PCI%20DSS%20General/PCI-DSS-Scoping-and-Segmentation-Guidance-for-Modern-Network-Architectures.pdf)
[title](https://www.awarex.com/terms-conditions-confidential-information)
[title](https://www.techtarget.com/searchsecurity/definition/personally-identifiable-information-PII)
[title](https://www.investopedia.com/terms/p/personally-identifiable-information-pii.asp)
[title](https://piwik.pro/blog/what-is-pii-personal-data/)










