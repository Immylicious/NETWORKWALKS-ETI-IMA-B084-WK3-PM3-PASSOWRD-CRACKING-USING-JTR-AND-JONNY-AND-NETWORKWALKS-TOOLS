# Week 3 Project: Password Cracking and Hash Extraction

**Program:** Cybersecurity & Ethical Hacking — Networkwalks (Batch B084) 
**Modules Covered:**  
* **Module 1:** Password Cracking with John the Ripper (JTR & Johnny GUI)
* **Module 2:** Password Cracking with Networkwalks Web Tools

---

## 1. Project Overview
This project explores password security auditing and hash-based password recovery across two lab modules. The objective was to extract the cryptographic password hash from a locked PDF document (`My Locked PDF1.pdf`) and recover the plaintext password using both local desktop utilities (John the Ripper / Johnny GUI) and browser-based dictionary attack tools (Networkwalks Hash Calculator & Password Cracker).

---

## 2. Tools & Technologies Used
* **John the Ripper (JTR 1.9.0-jumbo-1):** Command-line password security auditing and recovery tool.
* **Johnny GUI (v2.2):** Graphical user interface for managing John the Ripper sessions and attacks.
* **Online Hash Crack (`pdf2john`):** Web utility for extracting JTR/Hashcat-compatible hashes from PDF files.
* **Networkwalks Hash Calculator:** Browser-based cryptographic hashing and local PDF hash extraction tool.
* **Networkwalks Password Cracker:** Browser-based dictionary attack tool for matching wordlists against extracted `$pdf$` hashes.
* **Environment:** Windows PC & Adobe Acrobat Reader DC.

---

## 3. Methodology & Execution

### Module 1: Password Cracking with JTR & Johnny GUI
1. **Environment Setup:** Downloaded and extracted `john-1.9.0-jumbo-1-win64` alongside `johnny_2.2_win.zip`. Installed Johnny GUI and linked its executable path to `john.exe` inside the `/run` directory.
2. **Hash Extraction:** Uploaded `My Locked PDF1.pdf` to the `pdf2john` hash extractor to retrieve the underlying `$pdf$4*4*128*...` hash string.
3. **Hash Formatting:** Saved the clean hash string into a plain text file (`hash1.txt`) using Notepad (ensuring no extraneous wrapper characters remained).
4. **Cracking Execution:** Loaded `hash1.txt` into Johnny GUI (`Open password file`) and initiated the attack (`Start new attack`).
5. **Verification:** Johnny successfully cracked the hash, revealing the plaintext password `password1`. Entered the password into Adobe Acrobat Reader to unlock the file and verify the completion flag (`networkwalks_flag1.pdf`).

### Module 2: Password Cracking with Networkwalks Web Tools
1. **Local Hash Extraction:** Opened the Networkwalks Hash Calculator in a web browser, navigated to the **PDF** tab, and loaded `My Locked PDF1.pdf` to locally parse and extract the `$pdf$` hash without uploading the file to an external server.
2. **Dictionary Attack:** Copied the full `$pdf$` hash into the Networkwalks Password Cracker tool.
3. **Password Recovery:** Executed the dictionary attack using the built-in 100-word list. The tool tested candidate words against the hash and matched `password1` at 91% progress.
4. **Verification:** Unlocked the encrypted PDF using the recovered password to confirm access.

---

## 4. Key Concepts & Takeaways
* **Encryption vs. Hashing:** Encryption is a reversible, two-way process requiring a decryption key to restore plaintext, whereas hashing is an irreversible, one-way mathematical function that converts input data into a fixed-length message digest.
* **Vulnerability of Weak Passwords:** Simple, common passwords (such as `password1` or `123456`) can be cracked in seconds using standard wordlists.
* **Defense Best Practices:** Enforcing password length (12+ characters), complexity (mixed uppercase, lowercase, numbers, and symbols), and avoiding dictionary words significantly increases the computational time required for brute-force or dictionary attacks.

---

## 5. Screenshots


<img width="1912" height="981" alt="Screenshot 2026-11-19 193503" src="https://github.com/user-attachments/assets/95072de4-5945-420b-8abf-a9ec5f2c1b55" />


<img width="1740" height="930" alt="Screenshot 2026-11-19 222253" src="https://github.com/user-attachments/assets/e6d81c77-4835-4c5d-ba75-fb8a9d430294" />


<img width="1507" height="928" alt="Screenshot 2026-11-19 222241" src="https://github.com/user-attachments/assets/88a6e396-9c99-4a8e-86ff-e6baf473ce5c" />


<img width="1918" height="927" alt="Screenshot 2026-11-19 195456" src="https://github.com/user-attachments/assets/8bd49780-484a-4b72-94ee-981cf741a95a" />


<img width="882" height="690" alt="Screenshot 2026-11-19 195308" src="https://github.com/user-attachments/assets/ad75bd47-c8a2-4ab9-a0c6-27efacab5d38" />


<img width="703" height="457" alt="Screenshot 2026-11-19 195344" src="https://github.com/user-attachments/assets/6c172480-48e2-434c-b692-00b1bcf8d04b" />


![Uploading Screenshot 2026-11-19 195405.png…]()
