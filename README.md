# Cybersecurity checklist for a developer:

- NEVER ever store password data in plain text!
- ALWAYS obfuscate password data with a _hash algorithm_ + _salt_!
  - **Argon2** (recommended), PBKDF2, SHA256
- _salting_ makes each password unique -> cannot be reverse engineered by sheer knowledge of password and hashing algorithm
- always generate a unique random salt for each password
- user-identification should ALWAYS happen in backend!
- prohibit logging in after n attempts (to combat brute forcing)

##

- Secure password conventions for users:

  - at least 12-16 characters long (preferably longer), long random sentences are a good choice
  - prohibit inputting already known or breached passwords (Pwned Passwords API)
  - preferably a combination of capital and non-capital letters, numbers and symbols

##

- use already HTTPS/SSL during _dev_:

  - Self-signed SSL Certificate during _dev_
  - Real certificate from for ex. LetsEncrypt when _release_
  - remember to renew certificates

##

- make a systematic and planned updating cycle!

  - Keep Programs + OS + Libraries always updated
  - stay up-to-date about known vulnerabilities
  - penetration tests
  - vulnerability scanner

##

- do _hardening_ for devices and servers:

  - stricten cybersecurity settings
  - disable unnecessary services
  - delete unnecessary users
  - uninstall unnecessary programs

##

- storage of secrets (API-keys, database user accounts and passwords, other confidential data that enables access to systems):

  - NEVER ever store secrets inside repo!
  - use a centralized secret-management tool with secure cryptography practices (for ex. AWS IAM)

##

- Some forms of cyberthreats:

  - Man In The Middle
  - SQL-Injection
  - Client-Side Code Injection
  - Broken authentication / session-control
  - Insecure Direct Object References
  - Protocol Downgrade (HTTPS -> HTTP)
  - Accidental configuration mistakes
  - Accidentally revealing sensitive data
    <br>
    <br>
  - Unsafe APIs
  - Lack of proper logging and surveillance
  - 3rd-party-dependancies (attack-vectors through them)
  - Denial of Service / Distributed Denial of Service
  - Browser history leaks
  - Cookie hijacking / injection
  - Confidential information in an email (email is not encrypted at all)

##

- How to prevent common cyberattacks (Man In The Middle, SQL-Injection, Client-Side Code Injection, DoS / DDoS):

  - Use a VPN when connected to public wifi
  - Make sure SSL is up-to-date, certificates and all
  - Use MFA whenever possible, use strong passwords
  - Use End-to-End Encryption in general
  - Accept only specific syntax of data into forms (regex useful here?)
    - Strict enough rules also help against execution of Client-Side Code
    - (This should ALWAYS happen in backend-side! )
  - Change all unnecessary user-inputted characters to strings
  - Strip unnecessary rights from database users
  - Protect cookies (for ex. bind cookies to specific IP-addresses and accept only those)
  - Set up Web Application Firewall (WAF) rules
  - DDoS protection services (for ex. CloudFlare has one)
