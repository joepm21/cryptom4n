🔐 Cryptom4n v1.0
Cryptom4n is a powerful and user-friendly desktop application built with Python that provides military-grade file encryption and decryption capabilities. Designed with security and ease of use in mind, it allows users to protect their sensitive files with strong AES-256 encryption.

🚀 Features

🔒 Core Encryption

 - AES-256-CBC Encryption: Industry-standard encryption algorithm
 - PBKDF2-HMAC-SHA256: Secure key derivation from passwords
 - CBC Mode with Random IV: Enhanced security through initialization vectors
 - PKCS7 Padding: Proper data padding for block cipher operations

🛡️ Security Features
 
 - Automatic File Cleanup: Original files are securely removed after encryption
 - Salt-based Key Generation: Unique salt for each encryption operation
 - Password Protection: Strong password-based key derivation
 - Secure File Handling: Encrypted files contain salt and IV for proper decryption

💻 User Interface

 - Intuitive GUI: Built with tkinter for cross-platform compatibility
 - Real-time Logging: Terminal-style output with timestamps
 - File Browser: Easy file selection dialog
 - Visual Feedback: Color-coded status messages and emojis
 - One-Click Clear: Clear all fields and logs with a single button

📦 Installation

Prerequisites

 - Python 3.6 or higher
 - Required packages: cryptography

# Clone the repository
    git clone https://github.com/joepm21/cryptom4n.git
    cd cryptom4n

# Install dependencies
    pip install cryptography

# Run the application
    python cryptom4n.py

🎯 Usage

Encryption Process
 
 1. Select File: Click "Browse 🔍" to choose the file you want to encrypt
 2. Enter Password: Provide a strong password for encryption
 3. Encrypt: Click "Encrypt 🔒" to secure your file
 4. Result: Original file is replaced with .encrypted version

Decryption Process

 1. Select Encrypted File: Choose a file with .encrypted extension
 2. Enter Password: Use the same password used for encryption
 3. Decrypt: Click "Decrypt 🔑" to restore the original file
 4. Result: Encrypted file is replaced with the original decrypted version

Clear All

- Click "Clear All 🗑️" to reset the entire interface:
  * Clear all logs and terminal output
  * Reset file selection field
  * Clear password field
  * Reset status messages

🔧 Technical Details

Encryption Algorithm

# Key components:
- Algorithm: AES-256-CBC
- Key Derivation: PBKDF2 with 100,000 iterations
- Hash: SHA256
- Salt: 16 bytes random
- IV: 16 bytes random
- Padding: PKCS7

File Structure

Encrypted files contain:

 - Bytes 0-15: Salt
 - Bytes 16-31: Initialization Vector (IV)
 - Bytes 32-end: Encrypted data

Security Considerations

 - Strong Passwords: Use complex passwords for better security
 - File Backup: Original files are permanently deleted after encryption
 - Key Management: Remember your password - it cannot be recovered
 - Secure Environment: Run on trusted systems only

📋 Requirements

Python Packages

 * cryptography >= 3.0
 * tkinter (usually included with Python)

System Requirements

 * Windows, macOS, or Linux
 * 100MB free disk space
 * Python 3.6+

🛠️ Development

Code Architecture

 - FileEncryptor Class: Handles all cryptographic operations
 - App Class: Manages GUI and user interactions
 - Modular Design: Separate concerns for UI and encryption logic

⚠️ Security Disclaimer

🔐 Is it 100% Secure?

No system is 100% secure, but Cryptom4n provides:
✅ Very high security against common attackers
✅ Robust protection with strong passwords
✅ Solid implementation without known vulnerabilities

Recommended Password Practices:

 - Use 12+ characters with uppercase, lowercase, numbers, and symbols
 - Avoid dictionary words and common patterns
 - Don't reuse passwords across different files
 - Use a password manager for better security

🐛 Troubleshooting

Common Issues

1. "File not found": Ensure the file path is correct
2. Decryption errors: Verify the password and file extension
3. Permission errors: Check file/folder permissions
4. Memory errors: Large files may require more system resources

Logs

The application provides detailed logs in the terminal-style output panel, including:

 - Timestamps for all operations
 - File sizes and processing times
 - Success/error messages
 - Step-by-step operation details

🤝 Contributing

We welcome contributions! Please feel free to submit pull requests, report bugs, or suggest new features.

Areas for Improvement

 - Additional encryption algorithms
 - Cloud storage integration
 - Batch file processing
 - Enhanced UI themes
 - Command-line interface version

👨‍💻 Author
Created by j03 💀

⭐ If you find this project useful, please give it a star on GitHub!

🔐 Remember: With great encryption power comes great responsibility!
