# Week 3 Project: Password Cracking and Hash Extraction

**Program:** Cybersecurity & Ethical Hacking — Networkwalks (Batch B084)[cite: 1, 16]  
**Modules Covered:**  
* **Module 1:** Password Cracking with John the Ripper (JTR & Johnny GUI)[cite: 2]  
* **Module 2:** Password Cracking with Networkwalks Web Tools[cite: 17]  

---

## 1. Project Overview
This project explores password security auditing and hash-based password recovery across two lab modules[cite: 2, 17]. The objective was to extract the cryptographic password hash from a locked PDF document (`My Locked PDF1.pdf`) and recover the plaintext password using both local desktop utilities (John the Ripper / Johnny GUI) and browser-based dictionary attack tools (Networkwalks Hash Calculator & Password Cracker)[cite: 2, 17, 21].

---

## 2. Tools & Technologies Used
* **John the Ripper (JTR 1.9.0-jumbo-1):** Command-line password security auditing and recovery tool[cite: 3, 5].
* **Johnny GUI (v2.2):** Graphical user interface for managing John the Ripper sessions and attacks[cite: 2, 3].
* **Online Hash Crack (`pdf2john`):** Web utility for extracting JTR/Hashcat-compatible hashes from PDF files[cite: 7].
* **Networkwalks Hash Calculator:** Browser-based cryptographic hashing and local PDF hash extraction tool[cite: 17, 18, 19].
* **Networkwalks Password Cracker:** Browser-based dictionary attack tool for matching wordlists against extracted `$pdf$` hashes[cite: 17, 21].
* **Environment:** Windows PC & Adobe Acrobat Reader DC[cite: 2, 14, 17].

---

## 3. Methodology & Execution

### Module 1: Password Cracking with JTR & Johnny GUI
1. **Environment Setup:** Downloaded and extracted `john-1.9.0-jumbo-1-win64` alongside `johnny_2.2_win.zip`[cite: 3, 5]. Installed Johnny GUI and linked its executable path to `john.exe` inside the `/run` directory[cite: 4, 5].
2. **Hash Extraction:** Uploaded `My Locked PDF1.pdf` to the `pdf2john` hash extractor to retrieve the underlying `$pdf$4*4*128*...` hash string[cite: 7, 8].
3. **Hash Formatting:** Saved the clean hash string into a plain text file (`hash1.txt`) using Notepad (ensuring no extraneous wrapper characters remained)[cite: 8, 9, 10].
4. **Cracking Execution:** Loaded `hash1.txt` into Johnny GUI (`Open password file`) and initiated the attack (`Start new attack`)[cite: 11, 12].
5. **Verification:** Johnny successfully cracked the hash, revealing the plaintext password `password1`[cite: 13]. Entered the password into Adobe Acrobat Reader to unlock the file and verify the completion flag (`networkwalks_flag1.pdf`)[cite: 14].

### Module 2: Password Cracking with Networkwalks Web Tools
1. **Local Hash Extraction:** Opened the Networkwalks Hash Calculator in a web browser, navigated to the **PDF** tab, and loaded `My Locked PDF1.pdf` to locally parse and extract the `$pdf$` hash without uploading the file to an external server[cite: 18, 19].
2. **Dictionary Attack:** Copied the full `$pdf$` hash into the Networkwalks Password Cracker tool[cite: 20, 21].
3. **Password Recovery:** Executed the dictionary attack using the built-in 100-word list[cite: 21]. The tool tested candidate words against the hash and matched `password1` at 91% progress[cite: 22].
4. **Verification:** Unlocked the encrypted PDF using the recovered password to confirm access[cite: 22, 23].

---

## 4. Key Concepts & Takeaways
* **Encryption vs. Hashing:** Encryption is a reversible, two-way process requiring a decryption key to restore plaintext, whereas hashing is an irreversible, one-way mathematical function that converts input data into a fixed-length message digest[cite: 15, 23].
* **Vulnerability of Weak Passwords:** Simple, common passwords (such as `password1` or `123456`) can be cracked in seconds using standard wordlists[cite: 13, 22, 23].
* **Defense Best Practices:** Enforcing password length (12+ characters), complexity (mixed uppercase, lowercase, numbers, and symbols), and avoiding dictionary words significantly increases the computational time required for brute-force or dictionary attacks[cite: 23].

---

## 5. Screenshots
*(Place your lab execution screenshots in a `/screenshots` directory and link them below)*
* `screenshots/01-johnny-setup.png` — Configuring `john.exe` inside Johnny GUI[cite: 5]
* `screenshots/02-pdf-hash-extraction.png` — Extracting the `$pdf$` hash[cite: 8, 19]
* `screenshots/03-johnny-cracked.png` — Password recovered in Johnny GUI (`password1`)[cite: 13]
* `screenshots/04-nw-password-cracker.png` — Dictionary attack match via Networkwalks Password Cracker[cite: 22]
* `screenshots/05-flag-captured.png` — Unlocked PDF confirming flag capture[cite: 14, 23]
