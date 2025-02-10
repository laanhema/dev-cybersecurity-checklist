# Cybersecurity checklist for a developer:

- NEVER ever store password data in plain text!
- ALWAYS obfuscate password data with a _hash algorithm_ + _salt_!
  - **Argon2** (recommended), PBKDF2, SHA256
- _salting_ makes each password unique -> cannot be reverse engineered by sheer knowledge of password and hashing algorithm
- always generate a unique random salt for each password
- user-identification should ALWAYS happen in backend!
- prohibit logging in after n attempts (to combat brute forcing)

##

- secure password conventions for users:

  - at least 12-16 characters long (preferably longer), long random sentences are a good choice
  - prohibit inputting already known or breached passwords (Pwned Passwords API)
  - preferably a combination of capital and non-capital letters, numbers and symbols

##

- use already HTTPS/SSL during _dev_:
  - Self-signed SSL Certificate during _dev_
  - Real certificate from for ex. LetsEncrypt when _release_
  - remember to renew certificates

##

- make a systematic and planned updating cycle
  - Keep Programs + OS + Libraries always updated
  - stay up-to-date about known vulnerabilities
  - vulnerability scans + penetration-tests
