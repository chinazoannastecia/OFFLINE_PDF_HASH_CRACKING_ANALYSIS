# OFFLINE_PDF_HASH_CRACKING_ANALYSIS
This project documents a controlled cybersecurity lab focused on recovering passwords from protected PDF files by extracting PDF hashes and performing dictionary attacks... The exercise compares a local John the Ripper (JTR) / Johnny workflow with the Networkwalks online PDF hash cracking service.
## Lab Information

| Field | Details |
| :--- | :--- |
| **Author** | Ugwuoke, Annastecia |
| **Role** | Cyber security Intern |
| **Program / Batch** | Networkwalks Internship / B083C |
| **Instructor** | Waqas Karim CCIE |
| **Date** | September 27, 2026 |
| **Classification** | Training |
### **Objectives**

*   To understand and perform offline password recovery for encrypted PDF documents through hash extraction and dictionary-based cracking techniques.
*   To analyze and document the difference between cracking with a locally installed John the Ripper / Johnny setup and using the cloud-based tools provided by Networkwalks.
*   ### **Environment & Tools**

| Category | Tools / Details |
| :--- | :--- |
| **Operating System** | Windows 11 (64-bit) |
| **Hash Extraction** | OnlineHashCrack PDF Hash Extractor, Networkwalks PDF Hash Calculator |
| **Password Cracking** | John the Ripper Jumbo (CLI), Johnny (GUI for JTR), Networkwalks Online PDF Cracker |
### **Methodology**
#### **Module 1 — John the Ripper (JTR)**

1.  **Hash Extraction:** The hashes were extracted from the protected PDF files using the PDF hash extractor tool on `onlinehashcrack.com` to generate the `$pdf$` format hashes.
2.  **Preparation:** All extracted hash strings were saved into separate `.txt` files to prepare them for offline cracking.
3.  **Cracking Process:** The hash files were loaded into Johnny, the graphical user interface for John the Ripper, where a dictionary attack using the built-in wordlist was launched to recover the cleartext passwords.
4.  #### **Module 2 — Networkwalks Tools**

1.  **Hash Extraction:** The target PDF files were uploaded directly to the Networkwalks PDF Hash Calculator to automatically extract and parse the file hashes.
2.  **Cracking Process:** The extracted hashes were then submitted to the Networkwalks Online PDF Password Cracker, where its built-in wordlist attack was executed to recover the passwords.
### **Results**

The dictionary-based attacks successfully recovered the passwords for all three encrypted PDF files, which allowed the hidden CTF flags inside each document to be retrieved.
| Target | Recovered Password | Captured Flag | Methods Used |
| :--- | :--- | :--- | :--- |
| **1** | `password1` | `nw{networkwalks_flag_jtr_270521-1}` | JTR / Johnny; Networkwalks Password Cracker |
| **2** | `password1` | `nw{networkwalks_persistence_jtr_270521}` | JTR / Johnny; Networkwalks Password Cracker |
| **3** | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` | JTR / Johnny; Networkwalks Password Cracker |

Target 1
Extracted Hash: $pdf$4*4*128*-1028*1*16*0853f2c...
Cracked Password: password1
Captured Flag: nw{networkwalks_flag_jtr_270521}

### **Evidence**

#### **Proof of Cracking**

![Lab Evidence](Screenshot%202026-09-27%20063603.png)
### **Evidence / Screenshots**

#### **First Target Proof**
![First Proof](Screenshot%202026-09-27%20055457.png)

#### **Last Target Proof**
![Last Proof](Screenshot%202026-09-27%20070442.png)


Target 2.

Extracted Hash: $pdf$4*4*128*-1028*1*16*ca7f72f...

Cracked Password: password1

Captured Flag: nw{networkwalks_persistence_jtr_270521}

Target 3
Extracted Hash: $pdf$4*4*128*-1028*1*16*34eb542...
Cracked Password: 1qaz2wsx
Captured Flag: nw{networkwalks_flag_260821_1}
Mitigation & Remediation Strategies
To reduce the likelihood of successful offline dictionary attacks, the following controls and policies should be implemented:

1. Enforce Strong Passphrases
Dictionary attacks rely heavily on common words and simple alphanumeric sequences. Long passphrases with high entropy make dictionary and brute-force attacks substantially more difficult.

2. Avoid Predictable Patterns
Users should avoid standard keyboard walks such as 1qaz2wsx or appending numbers to common words such as password1, because modern wordlists commonly test these patterns.

3. Use Strong Encryption Standards
Files should be secured using robust encryption algorithms such as AES-256 rather than legacy encryption methods, increasing the effort required for cracking attempts.

4. Consider Certificate-Based Security
For highly sensitive documents, certificate-based encryption can reduce reliance on human-selected passwords.

Conclusion
The exercises demonstrated that predictable passwords such as password1 and 1qaz2wsx can be recovered using standard wordlists and readily available tools. The results reinforce the importance of strong password selection, avoidance of predictable patterns, and appropriate document-encryption controls when protecting files against offline hash-cracking attempts.

Ethics & Scope
This report documents a controlled training exercise performed against designated lab files. Password-recovery and hash-cracking techniques should only be applied to systems, files, and accounts for which you have explicit authorization.

Project: Offline PDF Hash Cracking Analysis
Training: Networkwalks Internship / B083C
Author: Ugwuoke, Annastecia
