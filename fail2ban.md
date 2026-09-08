Fail2ban helps protect the server from repeated suspicious login attempts.

During this lab I used Fail2ban to monitor SSH authentication attempts and
temporarily ban IP addresses with repeated failures.


I installed Fail2ban using the Debian package manager:

```bash
apt update
apt install fail2ban
I also checked the Fail2ban status using:

```bash
fail2ban-client status
The server had one active jail:
Jail list: sshd
The sshd jail monitors SSH authentication attempts.
SSH Jail
I checked the SSH jail using:
fail2ban-client status sshd
The status showed information about failed and banned connections:
Currently failed: 2
Total failed: 21
Currently banned: 1
Total banned: 1
Configuration
The Fail2ban configuration used:
maxretry = 5
findtime = 600
bantime = 600
This means that an IP can be banned after 5 failed attempts within 10 minutes.
The ban lasts for 10 minutes.
Banned IP Addresses
Fail2ban detected repeated failed SSH authentication attempts and temporarily banned suspicious IP addresses.
I used the sshd jail status to check the current number of banned IP addresses.
