# XDR_C2
**A menu-driven Python multi-tool for security research, combining a socket-based remote command shell, file cryptography, a ransomware simulation, and LSB steganography.**

[![License](https://img.shields.io/github/license/DarkSoulEngineer/XDR_C2)](LICENSE)
[![Python](https://img.shields.io/badge/language-Python-3776AB)](https://www.python.org/)

## Table of Contents

- [Description](#description)
  - [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Description

XDR_C2 is a command-line multi-tool written in Python that bundles several security and cryptography utilities behind a single interactive menu. It is intended for penetration testing practice, ethical hacking exercises, and cybersecurity research in controlled environments. Each option maps to an independent module under the `Tools/` directory, so modules can also be read and studied on their own.

### Features

- **Remote Command**: A command-and-control style shell built on TCP sockets. The `master` component listens for a connection and sends commands; the `slave` component executes them and returns output, demonstrating a basic remote-shell protocol with length-prefixed messages.
- **Cryptography**: File encryption and decryption using the `cryptography` library (Fernet symmetric encryption). Keys are generated on first use and stored under `Assets/Ransomware/`.
- **Ransomware**: An educational ransomware simulation that overwrites a target file with an HMAC-SHA256 digest, illustrating how ransomware destroys recoverable data. For research and demonstration purposes only.
- **Steganography**: Hides and extracts text within images using the least-significant-bit (LSB) technique via Pillow. Image assets are handled under `Assets/Steganography/`.
- **Contact**: Displays developer contact information from `Assets/App/Contact`.

## Requirements

- Python 3.x
- Dependencies (specified in `requirements.txt`):
  - `cryptography==3.4.8`
  - `Pillow==8.3.2`
  - `pyfiglet==0.8.post1`
  - `pysocks==1.7.1`

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/DarkSoulEngineer/XDR_C2.git
   ```

2. Navigate to the project directory:

   ```bash
   cd XDR_C2
   ```

3. Install the dependencies:

   ```bash
   pip install -r requirements.txt
   ```

4. Run the application:

   ```bash
   python app.py
   ```

## Usage

Launch `python app.py` to print the banner and open the interactive menu. Type the number of the tool you want at the `xdr >` prompt:

1. **Remote Command**: choose `1` to start the master (listener) or `2` to start the slave (client).
2. **Cryptography**: encrypt or decrypt files located in `Assets/Ransomware/`.
3. **Ransomware**: run the ransomware simulation against a file in `Assets/Ransomware/`.
4. **Steganography**: hide or extract data in images under `Assets/Steganography/`.
5. **Contact**: show developer contact details.
6. Exit the tool.

A walkthrough of the steganography module is available on [Loom](https://www.loom.com/share/26082fe5466c493799f002e7ece6bcd1).

> **Note:** The remote command, ransomware, and steganography modules operate on local files and localhost sockets by default. Use them only in environments you own or are authorized to test.

## License

GPL-3.0. See [LICENSE](LICENSE).
