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
Module 1 — John the Ripper (JTR)
Module 2 — Networkwalks Tools
Hash Extraction: The target PDF files were uploaded to the Networkwalks Hash Calculator to parse the files and extract their hashes within the web browser.
Cracking Process: The extracted hashes were supplied to the Networkwalks Password Cracker, where its built-in wordlist attack was executed to recover the passwords.
Hash Extraction: The online tool at onlinehashcrack.com was used to extract the $pdf$ hashes from the locked PDF files.
Preparation: The extracted hash values were saved into .txt files for local processing.
Cracking Process: The hash files were imported into the Johnny GUI, which provides a graphical interface for JTR, and a dictionary attack was executed to recover the passwords.
### **Results**

The dictionary-based attacks successfully recovered the passwords for all three encrypted PDF files, which allowed the hidden CTF flags inside each document to be retrieved.
| Target | Recovered Password | Captured Flag | Methods Used |
| :--- | :--- | :--- | :--- |
| **1** | `good-luck` | `nw{cybersecurity_flag_captured_2608}` | JTR / Johnny; Networkwalks Password Cracker |
| **2** | `password1` | `nw{networkwalks_persistence_jtr_270521}` | JTR / Johnny; Networkwalks Password Cracker |
| **3** | `1qaz2wsx` | `nw{networkwalks_flag_260821_1}` | JTR / Johnny; Networkwalks Password Cracker |
