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
