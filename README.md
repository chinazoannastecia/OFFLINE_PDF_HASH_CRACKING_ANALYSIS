# OFFLINE_PDF_HASH_CRACKING_ANALYSIS
This project documents a controlled cybersecurity lab focused on recovering passwords from protected PDF files by extracting PDF hashes and performing dictionary attacks. The exercise compares a local John the Ripper (JTR) / Johnny workflow with the Networkwalks online PDF hash cracking service.
## Lab Information

| Field | Details |
| :--- | :--- |
| **Author** | Ugwuoke Annastecia Chinazo |
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
| **1** | `good-luck` | `nw{cybersecurity_flag_captured_2608}` | JTR / Johnny; Networkwalks Password Cracker |
| **2** | `password1` | `nw{networkwalks_persistence_jtr_270521}` | JTR / Johnny; Networkwalks Password Cracker |
| **3** | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` | JTR / Johnny; Networkwalks Password Cracker |

Target 1
Extracted Hash: $pdf$4*4*128*-1028*1*16*0853f2c...
Cracked Password: password1
Captured Flag: nw{networkwalks_persistence_jtr_270521}
### **Evidence / Screenshots**

#### **Target 1 Proof**
![Target 1 - JTR Cracking](Screenshot%202026-09-27%20063518.png)

