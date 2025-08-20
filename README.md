# **Hybrid Data Asset Management Executive Summary**

### **Project Overview**

This project outlines the design and implementation of a hybrid data asset management and disaster recovery system for Monosordos Productions, a fictional multimedia company specializing in remote film production. The system was engineered to provide robust data security and business continuity while addressing the company's unique challenges, including a limited and predictable budget, high data traffic, and the need for security in remote regions.

### **Key Design and Security Features**

* **Hybrid Architecture:** The system uses a combination of on-premises **RAID 5 hard drives** and **cloud storage** to balance performance, cost, and security.  
* **3-2-1-0 Backup Rule:** The solution adheres to this industry best practice, maintaining three copies of all data on two different media types, with one copy stored off-site. The **"0"** is addressed through a weekly test restore process to validate backup integrity.  
* **Geographical Redundancy:** To protect data during travel, multiple physical drives are transported on separate flights by different crew members.  
* **Air-Gapped Backup:** An off-site drive remains disconnected from the internet, providing an ultimate defense against cyberattacks like ransomware.  
* **Role-Based Access Control:** The principle of **least privilege** is enforced, with specific permissions for administrators, editors, and uploaders.

### **Project Outcomes**

* **Proactive Security:** The implemented system has successfully prevented data loss from multiple incidents, saving the company thousands of dollars in potential costs.  
* **Increased Productivity:** The new automated backup system significantly reduced manual labor and prevented team exhaustion, leading to improved productivity.  
* **Strategic Foundation:** The project lays the groundwork for future enhancements, including automated health monitoring and multi-factor authentication, ensuring the system remains scalable and resilient as the company grows.

This project demonstrates a strong understanding of practical cybersecurity principles, from strategic planning and risk mitigation to hands-on implementation and continuous improvement.
