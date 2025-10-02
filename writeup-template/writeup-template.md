# [CTF_NAME] [YEAR] - [CHALLENGE_NAME] Writeup 🩸[BLOOD_STATUS]🩸
- **Author:** [YOUR_NAME]
- **Team:** [TEAM_NAME]
- **Date:** [DATE]
- **github:** [GITHUB_LINK]

## Challenge Information

- **Category:** [CATEGORY]
- **Challenge Name:** [CHALLENGE_NAME]
- **Description:** [CHALLENGE_DESCRIPTION]
- **Author:** [CHALLENGE_AUTHOR]
- **Points:** [POINTS]
- **Solves:** [SOLVES]

## TL;DR

**Required Skills:**
- **[Skill 1]:** [Description of required skill - e.g., Assembly knowledge, Web fundamentals, Cryptographic concepts]
- **[Skill 2]:** [Description of required skill - e.g., Python scripting, Network analysis, File formats]

**Techniques Covered:**
- **[Technique 1]:** [Description of technique - e.g., Buffer overflow, SQL injection, Frequency analysis]
- **[Technique 2]:** [Description of technique - e.g., ROP chain, XSS, Steganography]

---

## Initial Analysis

### File Information
```bash
$ file [filename]
# For multiple files:
$ file challenge_files/*
```

Output:
```
[file output - file type, architecture, etc.]
```

### Security Features (if applicable - binaries)
```bash
$ checksec [filename]
```

Output:
```
    Arch:       [architecture - x86-64, ARM, etc.]
    RELRO:      [relro_status - Full/Partial/No RELRO]
    Stack:      [canary_status - Canary found/No canary]
    NX:         [nx_status - NX enabled/disabled]
    PIE:        [pie_status - PIE enabled/disabled]
    Stripped:   [stripped_status - Yes/No]
```

### Network/Web Analysis (if applicable)
```bash
$ nmap -sV [target]
$ curl -I [url]
$ dirb [url]
```

### Key Observations
- **[Observation 1]:** [Description and implication - e.g., No stack canary = buffer overflow possible]
- **[Observation 2]:** [Description and implication - e.g., Weak encryption = crypto challenge]
- **[Observation 3]:** [Description and implication - e.g., Hidden data = steganography]

---

## Analysis

### [Phase 1 - e.g., Static Analysis, Source Code Review, File Examination]

[Detailed analysis of the challenge - adapt based on category]

**For PWN/Rev:** Static binary analysis, main functions, vulnerabilities
**For Web:** Source code analysis, endpoints, parameters
**For Crypto:** Algorithm analysis, keys, patterns
**For Forensics:** File analysis, metadata, artifacts
**For Misc:** Initial problem analysis, data format

![Static or initial analysis](images/static_analysis.png)

```[language]
[code snippet, configuration, or relevant data]
```

### [Phase 2 - e.g., Dynamic Analysis, Exploitation, Decryption]

[Detailed analysis of the challenge - second phase]

**For PWN:** Dynamic analysis, debugging, ROP chains
**For Web:** Payload testing, filter bypasses
**For Crypto:** Attack implementation, cipher breaking
**For Forensics:** Data extraction, timeline reconstruction
**For Misc:** Data processing, automation

![Dynamic analysis or process](images/dynamic_analysis.png)

### [Phase 3 - e.g., Payload Development, Final Exploitation] (if needed)

[Third phase if needed - final solution development]

### Important Findings
1. **[Finding 1]:** [Description - e.g., Buffer overflow at offset 72]
2. **[Finding 2]:** [Description - e.g., SQL injection in login form]
3. **[Finding 3]:** [Description - e.g., Hidden message in LSB of image]

---

## Solution

### [Step 1 - e.g., Initial Access, Vulnerability Discovery, Pattern Recognition]

[Description of solution step]

**For PWN:** Vulnerability discovery, offset calculation
**For Web:** Injection point identification, filter bypasses
**For Crypto:** Weakness identification, pattern analysis
**For Forensics:** Artifact location, data extraction
**For Misc:** Problem understanding, pattern identification

![First solution step](images/step1_solution.png)

```python
# [Description of code]
[solution code - adapt language based on challenge]
```

Output:
```
[expected output]
```

### [Step 2 - e.g., Exploitation, Attack Implementation, Data Processing]

[Description of solution step]

**For PWN:** Exploit development, ROP chain
**For Web:** Payload construction, exploitation
**For Crypto:** Attack implementation, cipher breaking
**For Forensics:** Detailed analysis, reconstruction
**For Misc:** Automation, batch processing

```python
# [Description of code]
[solution code]
```

### [Step 3 - e.g., Flag Retrieval, Final Payload, Solution Verification]

[Description of final step]

```python
# [Description of code - final payload/solution]
[solution code]
```

---

## Complete Solution

```python
#!/usr/bin/env python3

# Imports - adapt based on challenge type
from pwn import *           # For PWN
import requests            # For Web
from Crypto.Util.number import *  # For Crypto
import binascii           # For Forensics/Misc
import re                 # For pattern matching

# Configuration
# For PWN:
binary = ELF('./[binary_name]')
context.binary = binary
context.log_level = 'info'

# For Web:
# target_url = "http://[host]:[port]"
# session = requests.Session()

# For others:
# [specific configuration]

def conn(mode):
    """Connection function - adapt for challenge type"""
    if mode == 1:
        r = process(binary.path)        # PWN local
        # r = requests.get(target_url)  # Web
    elif mode == 2:
        r = gdb.debug(binary.path, """
            # GDB commands here
            """)
    elif mode == 3:
        r = remote("[host]", [port])    # PWN remote
        # r = requests.get("http://[host]:[port]")  # Web remote
    return r

def solve():
    """Main solution function"""
    # For PWN:
    r = conn(1)
    
    # For Web:
    # response = requests.get(target_url)
    
    # For Crypto:
    # ciphertext = "[encrypted_data]"
    
    # For Forensics:
    # with open('[file]', 'rb') as f:
    #     data = f.read()
    
    # [Solution steps here]
    
    # For PWN:
    r.interactive()
    
    # For others:
    # return flag

if __name__ == "__main__":
    solve()
```

---

## Flag

```
[flag_format]{[flag_content]}
```

---

## Alternative Approaches

### [Alternative 1]
[Description of alternative method that could work]

### [Alternative 2] 
[Description of another approach]

---

## Tools Used

- **[Tool 1]:** [Description - e.g., Ghidra for reverse engineering]
- **[Tool 2]:** [Description - e.g., Burp Suite for web testing]
- **[Tool 3]:** [Description - e.g., Python for automation]

---

## References

- [Reference 1 - e.g., Documentation, CVE, Research paper]
- [Reference 2 - e.g., Tool documentation, Tutorial]
- [Reference 3 - e.g., Similar writeups, Techniques]

---

## Lessons Learned

- **[Lesson 1]:** [What you learned from this challenge]
- **[Lesson 2]:** [Techniques that can be applied elsewhere]
- **[Lesson 3]:** [Mistakes to avoid in the future]

---

## Notes

- **Difficulty:** [Easy/Medium/Hard] 
- **Time taken:** [Approximate time]
- **Key insight:** [The main "aha" moment]
- **Additional notes:** [Any other observations or comments]