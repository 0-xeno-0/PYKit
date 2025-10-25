***PYKit: A Modular Security and Automation Framework***
PYKit is a command-line, object-oriented framework written in Python. It is designed to provide a simple, interactive menu for various security, network, and system automation tasks.
The project is built using a modular, class-based architecture, making it easy to extend and maintain. All modules share a centralized logger and a single requests.Session for efficient web operations.
A key part of the toolkit is its SecurityAnalysis module, which focuses on explaining defensive concepts related to common attacks rather than performing the attacks themselves.

### 🛠️ Key Features
The toolkit is organized into modules, each handling a specific domain:

1. ***Web & Recon***
**Download File:** Download a file from any URL to a specified destination.

**Get Page Headers:** Fetch and display the HTTP response headers for a given URL.

**Site Crawler:** Recursively crawl a website up to a specified depth to discover all internal links.

**Form Extractor:** Find and list all HTML <form> elements on a single webpage.

2. ***System Utilities***
**Secure Password Generator:** Generate a strong, random password of a user-defined length.

**Folder Organizer:** Automatically organize a messy folder by moving files into subdirectories (e.g., images, documents, archives) based on their file extensions.

3. **Network Operations**
**TCP Listener:** Start a multi-threaded TCP echo server on a specific host and port to listen for incoming connections.

**Interactive Host Connector:** Connect to a remote host and port and open an interactive shell session (using telnetlib).

4. ***Defensive Security Education***
Instead of including offensive tools, this module provides clear explanations on how to defend against common attacks:

Explain XSS Prevention: Details on Content Security Policy (CSP), Contextual Output Encoding, and Input Validation.

Explain C2 / Reverse Shell Defense: Focuses on Egress Filtering (blocking outbound traffic) and Process Monitoring.

Explain Brute-Force Defense: Covers Rate-Limiting, Account Lockout, and CAPTCHA implementation.

Explain Registry Persistence: Explains how attackers use Registry Run keys for persistence and how to detect it using tools like Autoruns.

### 🚀 Installation

## 1.  Clone or Download: The PYKit.py file from this repository.

## 2. Create a Virtual Environment (Recommended):
```Bash
python3 -m venv venv
source venv/bin/activate
```

## 3. Install Dependencies: PYKit relies on requests for web operations and beautifulsoup4 for HTML parsing.
```Bash
pip install requests beautifulsoup4
```

## 4. How to Use make the script executable (on Linux/macOS):
```Bash
chmod +x PYKit.py
```

## 5. Run the script:
```Bash

python3 PYKit.py
(or ./PYKit.py if you made it executable)
```

## Use the Menu: You will be presented with a main menu. Enter the number corresponding to the tool you wish to use and press Enter. Follow the on-screen prompts for each tool.


***Code Architecture***

The framework is intentionally designed with a clear object-oriented structure:

**PYKit (Main Class):** The core class that initializes all sub-modules and runs the main CLI menu loop.

**WebManager:** Handles all high-level HTTP interactions like getting page content and downloading files. It uses the shared requests.Session provided by PYKit.

**NetworkManager:** Manages all low-level TCP socket operations. This includes creating multi-threaded listeners and interactive clients.

**ReconManager:** Contains all information-gathering tools, such as the site crawler and form extractor.

**SystemManager:** Provides local system utilities like the password generator and folder organizer.

**SecurityAnalysis:** A "hub" class that contains nested sub-classes for each defensive module (VulnerabilityScanner, PersistenceAnalyzer, etc.). This module's purpose is purely educational.
