# Kali Linux-like Environment on macOS with Homebrew

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This guide provides step-by-step instructions to set up a Kali Linux-like penetration testing environment on macOS using Homebrew.

## Prerequisites

1. **Homebrew** - macOS package manager.
   If you don't have Homebrew installed, install it first:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **macOS Terminal or iTerm2** (optional for enhanced terminal experience).

---

## Step-by-Step Setup

### 1. Tap Additional Homebrew Repositories

Some tools require additional Homebrew repositories:
```bash
brew tap homebrew/cask
brew tap homebrew/core
```

### 2. Install Tools and Utilities

Run the following command to install the required tools:

```bash
brew install --formula wireshark nmap masscan nikto sqlmap aircrack-ng hcxtools hydra whois theharvester hashcat john python ruby netcat tcpdump gnupg binwalk && brew install --cask burp-suite zaproxy docker virtualbox
```

### 3. Install Volatility (Optional)

The `volatility` package is not available through Homebrew but can be installed manually:

#### Install via Python:
```bash
pip install volatility
```

#### Install from Source:
```bash
git clone https://github.com/volatilityfoundation/volatility.git
cd volatility
python setup.py install
```

---

### 4. Install Metasploit (Optional)

Metasploit is not available via Homebrew. You can install it via Docker or manually:

#### Option 1: Using Docker
```bash
docker pull metasploitframework/metasploit-framework
docker run -it --rm metasploitframework/metasploit-framework
```

#### Option 2: Manual Installation
```bash
curl https://raw.githubusercontent.com/rapid7/metasploit-framework/master/scripts/omnibus_installer.sh | bash
```

---

### 5. Post-Installation Setup

1. **Add Wireshark to PATH**:
   ```bash
   echo 'export PATH="/Applications/Wireshark.app/Contents/MacOS:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

2. **Launch Docker and VirtualBox**:
   - Start Docker Desktop from Applications.
   - Open VirtualBox for virtual machines.

---

## Tools Included

| Tool           | Description                                       |
|-----------------|---------------------------------------------------|
| Wireshark       | Packet analyzer                                   |
| Nmap            | Network scanner                                   |
| Masscan         | High-speed port scanner                          |
| Nikto           | Web server vulnerability scanner                 |
| Sqlmap          | SQL injection tool                               |
| Aircrack-ng     | Wireless network cracker                         |
| Hcxtools        | WPA handshake tools                              |
| Hydra           | Password brute-force tool                        |
| WhoIs           | Domain lookup utility                            |
| The Harvester   | Subdomain and email reconnaissance               |
| Hashcat         | GPU-accelerated password cracker                 |
| John the Ripper | Multi-platform password cracker                  |
| Python          | Programming language for scripting and tools     |
| Ruby            | Programming language for Metasploit and tools    |
| Netcat          | Networking utility                               |
| Tcpdump         | Command-line packet analyzer                     |
| GnuPG           | Encryption and signing utility                   |
| Binwalk         | Firmware analysis tool                           |
| Burp Suite      | Web application security testing tool            |
| OWASP ZAP       | Web application penetration testing tool         |
| Docker          | Containerized environments for penetration tools |
| VirtualBox      | Virtualization for running Kali Linux VMs        |

---

## Troubleshooting

- **Permission Errors**: Run commands with `sudo` if necessary, but avoid doing so unless required.
- **Missing Tools**: Some tools might require manual installation or alternative approaches (e.g., Docker containers).

---

## Contribute

Feel free to submit pull requests or open issues if you'd like to improve this guide or add more tools!
