### Security

#### Server

**Operating System**

1. I always keep the software and libraries frequently updated to the latest version (I'm using unattended-upgrades package)
2. I only install the software I know or research before installing, and only install it when necessary.
3. I always use a non-administrative account to protect my server against brute force attacks that attempt to guess my "root" password.

**Network Security**

1. I enable the firewall on both my server and VPC Google Cloud firewall, only opening ports that I allow access to.
2. I use SSH key authentication instead of passwords, and I have changed the default SSH port from 22 to another port and only allowing inbound SSH traffic from my IP addresses.
3. I have disabled root login via SSH.
4. I will enable Cloud IDS if chosen by the Celestia team to delegate in Cohort 2. Cloud IDS provides threat detection for intrusions, malware, spyware, and command-and-control attacks on my network.

#### Private keys

1. On ETH and ERC20 chains, I use separate wallets for daily activities, maintaining a low balance. For holding wallets and validator wallets, I use [safe.global](https://safe.global) and require 2 confirmations from my 2 Ledger wallets for any transaction.
2. On Cosmos and other chains where multisig isn't common, I always use a Ledger if it's supported.
3. Regarding the Ledger seed phrase, I split it into 2 parts, and both parts are AES-256 encrypted. One part is stored on the cloud, and the other part is stored on a USB. I used my code to encrypt/decrypt my seed phrase, the code is uploaded [here](https://github.com/suntzu93/aes_en_de_crypto_key/blob/main/main.py).

#### Others

1. Running a redundant node helps ensure that if my validator node is compromised, another can continue to operate.
2. Enable Google Authenticator 2FA for all my services and accounts.
3. I am always cautious with emails, double-checking URLs and email addresses.
4. I never download any files through email.
5. Passwords used for crypto accounts are different from those used for regular services.
6. I do not use cracked software or software from unknown sources.
7. I do not interact with contracts before verifying them, and I do not approve more funds than needed.
8. I always regularly back up important data such as the keys folder, wallet, etc., and of course, everything is securely encrypted.
9. Use SSL/TLS for all my web services.

