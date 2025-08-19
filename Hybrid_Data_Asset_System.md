# **Hybrid Data Asset Management & Disaster Recovery System**

### **Project Overview**

This document outlines the design and implementation of a hybrid data asset security system for Monosordos Productions, a multimedia company specializing in films for the Deaf. The project's goal was to create a robust and cost-effective solution that addresses the company's unique needs, including a limited and predictable budget, high data traffic, and the need for security in remote locations. The implemented solution balances security, accessibility, and cost by leveraging both on-premises hardware and cloud services.

### **System Architecture**

The implemented solution is a hybrid system that leverages both on-premises hardware and cloud services to balance security, accessibility, and cost.

* **On-Premises Storage:** The core of the system is a RAID 5 hard drive array with three 36TB drives. **Two of these drives are located on-site,** providing a strong balance of **redundancy**, performance, and storage capacity, as the failure of a single drive will not result in data loss.  
* **Cloud Storage:** A **cloud-based backup system** is used for offsite data protection. This provides an additional layer of security against physical disasters affecting the main office. This predictable cost structure was chosen to avoid the variable costs associated with high data transfer fees in a fully cloud-based system.  
* **Offsite Physical Storage:** The **third RAID 5 hard drive is used for offline, offsite storage.** This physical drive is kept in a separate, secure location and is not connected to the internet. This provides an **air-gapped** backup, offering a robust defense against cyberattacks, ransomware, and other network-based threats.

### **Data Asset Management**

The system follows a strict, multi-stage process to ensure all footage is securely stored from the moment it is captured.

1. **Initial Capture:** All footage is captured simultaneously on three separate devices: two SD cards and an external SSD. This provides immediate, on-location redundancy. The external SSD acts as the primary source, while the SD cards serve as immediate backup copies.  
2. **Remote Data Backup:** When a crew is in a remote location, a dedicated set of three SSDs is used for on-site footage backup. The raw recordings on the camera SSD and SD cards are kept intact until they can be securely transferred back to the main office. The three backup SSDs are transported back to the main office on separate flights with different crew members to mitigate the risk of a single travel-related data loss event. This provides an additional layer of **geographical redundancy** during transit.  
3. **Raw Footage Transfer:** Raw footage from the external SSD is copied to the master RAID 5 drive. The data remains on the SSD until it is successfully copied to the master drive, mirror drive, cloud, and the offsite drive, ensuring no single point of failure. A rotating set of three SSDs and six SD cards is used to facilitate this process.  
4. **Editing Workflow:** A separate external SSD serves as the dedicated work drive for all editing tasks. Once editing is complete, the finalized footage is saved back to the master drive. It remains on the work HD until all backups are confirmed.  
5. **Backup Automation:** The system uses a copy and clone application to automate the backup process.  
   * The **master drive** receives daily transfers of all new data.  
   * The **mirror drive** is backed up from the master drive on an hourly basis.  
   * The **cloud backup** of the master drive is performed nightly.  
   * The **offsite drive** is rotated on a weekly basis, ensuring a fresh copy of all assets is stored securely at a remote location.

This backup strategy aligns with the **3-2-1 backup rule** (3 copies of data, on 2 different media, with 1 offsite), a recognized industry best practice.

### **Security and Access Control**

To protect data from unauthorized access, the system includes a robust access control and encryption policy.

* **Data Encryption:** All internet traffic, including the nightly cloud backup, is encrypted using a **VPN (Virtual Private Network)**. This ensures data confidentiality and integrity during transit.  
* **Physical Drive Security:** The Master, Mirror, and Offsite drives are all **password-protected**.  
* **Role-Based Access Control:** Permissions are strictly managed to enforce the principle of **least privilege**.  
  * The **administrator** has full save and delete permissions.  
  * The **editor** has only save permissions.  
  * The person responsible for uploading to the website has only read permissions.

### **Risk Mitigation**

The security system was designed to address a number of key risks:

| Design Feature | Risk Mitigated |
| :---- | :---- |
| RAID 5 | Single hard drive failure |
| Offsite Drive Rotation | Physical disaster (fire, flood, theft) or ransomware attack |
| VPN Encryption | Data interception during transit |
| Password Protection | Unauthorized access to physical drives |
| Role-Based Access Control | Data tampering, accidental deletion, or unauthorized access by an employee |
| Rotating Drives | Hardware failure due to constant use |
| **Separate Flights for Drives** | **Data loss during travel or flight-related incidents** |

### **Operational Details & Validation**

To ensure the system's ongoing reliability and effectiveness, the following procedures have been established:

* A **weekly test restore process** is performed to validate backup integrity and ensure the system's ability to recover data. This aligns with the **3-2-1-0 backup rule** (3 copies of data, 2 different media, 1 offsite, with **0 errors**).  
* All drives are subject to a regular **audit and replacement schedule** to mitigate the risk of hardware failure due to age.

### **Propose Future Enhancements**

To ensure the system scales with the company's growth and remains resilient against new threats, the following enhancements are proposed:

* **Automated Monitoring and Alerting:** Implement a system to automatically monitor the health of all drives and send alerts if backups fail. This would move the company from a reactive to a proactive backup validation process.  
* **Multi-Factor Authentication (MFA):** Add an extra layer of security to all cloud storage access with MFA. This would significantly reduce the risk of a compromised password leading to a data breach.  
* **Increased Automation for Restore Testing:** Develop a script to automate a portion of the weekly test restore process. This would reduce the manual effort required and allow for more frequent testing.  
* **Formal Security Awareness Training:** Conduct mandatory and regular security awareness training for all employees on topics such as phishing, social engineering, and the importance of secure data handling.

### **Lessons Learned**

* **Implementation Challenges:** The biggest challenge during implementation was the reliance on team members to transport the hard drives. It would have been more efficient to use a hard drive transportation and storage service to ensure consistent and timely offsite backups.  
* **Initial Team Behavior:** The team initially had difficulty adapting to the new workflow of not editing video footage before it was fully backed up. However, with repeated reminders and consistent procedures, the new habits became routine, and productivity increased.  
* **System Scalability:** The current system has a lifespan of approximately three years before the hard drives become full. A fully cloud-based solution for headquarters would be more scalable and cost-effective in the long run.  
* **Productivity and Financial Gains:** The new automated backup system, both on-site and in remote locations, significantly reduced manual effort and prevented team exhaustion, leading to increased productivity. **More importantly, the system's robust recovery procedures have prevented data loss from a number of incidents, saving the company thousands of dollars in potential costs.**

### **Skills Demonstrated**

This project showcases a range of cybersecurity and IT skills:

* **Data Asset Management & Security:** Design and implementation of a comprehensive data security system.  
* **Hybrid Cloud Architecture:** Integration of on-premises hardware with cloud storage for optimal performance and security.  
* **Disaster Recovery & Business Continuity:** Implementation of a resilient backup strategy that addresses physical disasters, theft, and cyberattacks.  
* **Access Control:** Design and enforcement of a role-based access control system.  
* **Risk Mitigation:** Proactive identification and mitigation of key risks, including data loss, unauthorized access, and budget constraints.  
* **Strategic Thinking:** Development of a practical and cost-effective solution tailored to the specific needs of a small business.