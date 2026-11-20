# Password-Cracking-with-John-the-Ripper-NetworkWalks-Tools
# Week 3 – Practical Exploration of PDF Password Recovery

## Introduction

As part of my cybersecurity training at NetworkWalks Academy, I completed the Week 3 practical exercises focused on recovering passwords from encrypted PDF documents.

The exercises involved two different password recovery approaches: a locally executed password auditing utility and a browser-based recovery platform.

The main goal was to understand how password-protected documents can be assessed through hash extraction and dictionary-based testing.

## Lab 1: PDF Password Recovery Using John the Ripper

### Lab Objective

Investigate the security of an encrypted PDF by extracting its password hash and testing possible passwords with John the Ripper.

### Lab Environment

| Component | Details |
|---|---|
| Operating System | Kali Linux |
| Password Auditing Tool | John the Ripper |
| Hash Extraction | PDF2John |
| Wordlist | RockYou |
| Target Format | Encrypted PDF |

### Execution Details

**1. Environment Verification**

Confirmed the John executable was available:

```bash
which john
```

**2. PDF Hash Generation**

Located the PDF2John utility and used it to generate a hash file:

```bash
perl /usr/share/john/pdf2john.pl "My Locked PDF1.pdf" > hash1.txt
```

The resulting hash was stored separately for password auditing.

**3. Dictionary Preparation**

The RockYou dictionary was available in compressed form. Extracted it using:

```bash
sudo gzip -dk /usr/share/wordlists/rockyou.txt.gz
```

**4. Password Testing**

Started the dictionary-based recovery process:

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash1.txt
```

**5. Recovery Verification**

Displayed the recovered credentials:

```bash
john --show hash1.txt
```

### Lab Outcome

The dictionary attack successfully identified the PDF password.

**Recovered Password:** `good-luck`

**Flag Obtained:**

`nw{cybersecurity_flag_captured_2608}`

The recovered credential was used to access the protected document and view its completion page.

---

## Lab 2: Browser-Based PDF Password Recovery

### Lab Objective

Explore a web-based approach to PDF password auditing without installing a separate password recovery application.

### Platform and Resources

- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker
- Google Chrome
- Assigned encrypted PDF

### Execution Details

**1. Hash Extraction**

Opened the NetworkWalks Hash Calculator:

https://networkwalks.com/hash-calculator/

Selected the assigned encrypted PDF and allowed the application to identify its encryption information.

**2. Hash Collection**

Copied the generated PDF hash in its complete `$pdf$` format.

**3. Password Recovery Platform**

Navigated to:

https://networkwalks.com/password-cracker/

**4. Dictionary Configuration**

Inserted the extracted hash into the password recovery interface and selected the available built-in dictionary.

**5. Password Testing**

Initiated the recovery operation and monitored the candidate password testing process.

**6. Successful Recovery**

The application identified a matching password and displayed the successful recovery result.

### Lab Outcome

**Recovered Password:** `password1`

**Flag Obtained:**

`nw{networkwalks_flag1_jtr_270521_1}`

The password was used to access the encrypted PDF, revealing the lab completion page.

---

## Skills and Knowledge Developed

During these exercises, I gained practical exposure to:

1. Working with password-protected PDF documents.
2. Extracting password hash information.
3. Understanding dictionary-based recovery techniques.
4. Managing wordlists in Kali Linux.
5. Operating John the Ripper from the terminal.
6. Exploring browser-based password auditing utilities.
7. Recognizing the risks associated with predictable passwords.

## Comparison of Both Approaches

| Feature | John the Ripper | NetworkWalks Tools |
|---|---|---|
| Execution | Kali Linux | Web browser |
| Hash Extraction | PDF2John | Hash Calculator |
| Candidate Source | RockYou | Built-in dictionary |
| Recovery Method | Dictionary attack | Dictionary attack |
| Result | Successful | Successful |

## Final Lab Summary

Both practical exercises were completed successfully.

| Deliverable | Result |
|---|---|
| PM1 PDF hash extraction | Completed |
| PM1 password recovery | Successful |
| PM1 flag retrieval | Successful |
| PM2 PDF hash extraction | Completed |
| PM2 password recovery | Successful |
| PM2 flag retrieval | Successful |

## Conclusion

These practical exercises provided an opportunity to examine password security from two different technical perspectives.

Working with John the Ripper helped me understand command-line password auditing, while the NetworkWalks platform demonstrated a simplified browser-based recovery workflow.

The experience reinforced an important security principle: passwords should be sufficiently long, unique and difficult to predict.

**Overall Result: Both Week 3 essential practical modules completed successfully.**

Training Program: NetworkWalks Academy  
Project Week: 03  
Domain: Cybersecurity and Ethical Hacking  
Practical Focus: PDF Password Security and Recovery

*Testing was performed using the assigned educational lab documents.*
