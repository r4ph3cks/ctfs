# CTF Writeup Template

This directory contains a universal template for CTF writeups that can be adapted for any challenge category.

## Included Files

- `template_writeup.md` - Main template adaptable for all categories
- `images/` - Folder for screenshots and diagrams with usage guide
- `images/README.md` - Detailed guide about image types by category

## Supported Categories

The template is flexible and can be used for:

- **PWN** - Binary Exploitation
- **REV** - Reverse Engineering  
- **WEB** - Web Application Security
- **CRYPTO** - Cryptography
- **FORENSICS** - Digital Forensics
- **MISC** - Miscellaneous challenges
- **OSINT** - Open Source Intelligence
- **STEGO** - Steganography
- **MOBILE** - Mobile Application Security
- **HARDWARE** - Hardware challenges

## How to Use

1. **Copy the template:**
   ```bash
   cp template_writeup.md ../[challenge_name]/README.md
   ```

2. **Replace the marked fields:**
   - `[CTF_NAME]` - CTF name
   - `[CHALLENGE_NAME]` - Challenge name
   - `[CATEGORY]` - Category (PWN, WEB, etc.)
   - `[YOUR_NAME]` - Your name
   - And all other fields between brackets

3. **Adapt the sections:**
   - The template includes specific guidance for each category
   - Keep only the sections relevant to your challenge
   - Use the inline comments as a guide

4. **Add images:**
   - Create an `images/` folder in your writeup
   - Consult `images/README.md` for recommended types
   - Use descriptive names for images

## Recommended Folder Structure

```
challenge_name/
├── README.md              # Your writeup (based on template)
├── images/               # Screenshots and diagrams
│   ├── static_analysis.png
│   ├── exploit_demo.png
│   └── flag_capture.png
├── files/               # Original challenge files
├── solution/            # Solution scripts
│   ├── exploit.py
│   ├── solve.py
│   └── requirements.txt
└── notes/               # Notes and drafts
    └── research.md
```

## Usage Tips

### For PWN/REV:
- Include `checksec` information
- Add Ghidra/IDA screenshots
- Document offsets and gadgets

### For WEB:
- Capture requests/responses
- Document tested payloads
- Include source code analysis

### For CRYPTO:
- Explain the algorithm
- Show mathematical calculations
- Document found weaknesses

### For FORENSICS:
- Include hexadecimal analysis
- Document timeline of events
- Show extraction process

### For MISC:
- Explain problem logic
- Document found patterns
- Include automation scripts

## Template Features

- ✅ Adaptable for any category
- ✅ Well-structured sections
- ✅ Image support
- ✅ Syntax highlighted code
- ✅ TL;DR section for quick summary
- ✅ References and lessons learned
- ✅ Alternative approaches