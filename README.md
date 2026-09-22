# NETWORKWALKS-B083-WK3-PM-PM2-PROJECT-
PDF Password Cracking

## 1. Objective
Understand the risks of weak passwords by cracking a lab-generated password-protected PDF and learning the workflow: hash extraction -> cracking -> verification.

### 2. Environment
- **Host OS:** Windows 11
- **Target File:** Lab-provided PDF (My Locked PDF2.pdf)
- **Tools:**
    - John the Ripper 1.9.0 Jumbo (Windows build)
    - Johnny - GUI for John
    - Networkwalks.com - Hash Calculator
    - Networkwalks.com - Password Cracker (Online verifier)

### 3. Installation on Windows 11

1. Download John the Ripper Jumbo for Windows from openwall.com
2. Extract to `C:\john`
3. Verify: `C:\john\run\john.exe --list=formats`
4. Install Johnny GUI from `openwall.com/johnny/` and install

### 4. Methodology

**Step 1: Hash Extraction**
Extracted the PDF hash to convert it into a John-compatible format (`$pdf$*...`). This is required for offline cracking.

**Step 2: Cracking with Johnny**
- Open Johnny
- Click `Open password file` > Select hash file
- Click `Start new attack`
- Attack Type: Dictionary Attack (default wordlist)
- Result: `1/1 cracked - 100% complete` [Password redacted]

**Step 3: Verification with Networkwalks**
- Used **Hash Calculator** to confirm hash type
- Used **Password Cracker** tool on networkwalks.com to cross-verify
- Output: `PASSWORD CRACKED SUCCESSFULLY`
- Unlocked the original PDF and retrieved the completion flag `[REDACTED]`

### 5. Screenshots
- `johnny_cracked.png` - Shows 100% cracked status
- `networkwalks_verified.png` - Shows successful verification
  

### 6. Key Learnings
- Johnny is just a GUI wrapper; it needs the John core binary path set correctly.
- Weak dictionary passwords fall in seconds with a wordlist attack.
- Offline cracking proves why strong password storage (Argon2, bcrypt) is critical.

### 7. Mitigation / Blue Team Takeaway
1. Enforce minimum 12+ character passphrases
2. Block common passwords and dictionary words
3. Implement MFA
4. Use strong KDFs for password storage, not fast hashes like MD5/SHA1
5. Educate users on password managers

### 8. Challenges
- Initial path configuration error in Johnny on Windows 11
- Understanding PDF hash format

---
**Author:**Thomas Michael Anayochukwu

**Lab Source:** Networkwalks.com
