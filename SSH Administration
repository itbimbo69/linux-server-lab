Overview
SSH  is the primary method used to remotely access and administer the Debian VPS.
The server is publicly accessible on the internet, making secure remote administration an important part of this lab

Initial SSH Access
The VPS was accessed remotely using the OpenSSH client:
ssh root@SERVER_IP

This establishes an encrypted connection between the local machine and the remote server.
After authentication, commands entered in the terminal are executed directly on the VPS rather than on the local computer.

SSH Host Verification
During the first connection, SSH displayed a host authenticity warning and presented the server's public key fingerprint.
The fingerprint was accepted and stored by the SSH client

SSH Keys
SSH public-key authentication was explored and configured using a public/private key pair.
The two keys have different purposes:
Private key → remains on the client
Public key → installed on the server
The private key is used to prove ownership of the key pair and must never be shared.
The public key can safely be stored on the server and is used to verify the client's authentication attempt.
The server stores authorized public keys in:
~/.ssh/authorized_keys

SSH Configuration
The SSH configuration files were inspected in:
/etc/ssh/
The main server configuration file is:
/etc/ssh/sshd_config
The directory also contains the server's host keys, which identify the VPS itself to connecting SSH clients.
This helped distinguish between:
Host keys =identify the server
User SSH keys = authenticate users connecting to the server

Session and Login Investigation
Several Linux commands were used to inspect active and previous SSH sessions.
Current users
who
Displays users currently logged into the system.
Detailed system activity
w
Shows logged-in users, their sessions and current activity.
Previous logins
last -i
Displays historical login sessions together with IP addresses.
 
These commands were used to understand how remote access to the VPS works and to investigate unexpected login activity.

Authentication Logs
SSH authentication events were investigated using journalctl:
journalctl -u ssh
Failed authentication attempts were filtered with:
journalctl -u ssh | grep "Failed"
Invalid usernames were investigated with:
journalctl -u ssh | grep "Invalid user"
The logs revealed automated authentication attempts against the publicly accessible SSH service.
Examples included attempts using usernames like:
Ansible
Minecraft
www
user
This demonstrated that an internet-facing SSH service is continuously exposed to automated scanning and login attempts.

Security Considerations
The investigation highlighted several important SSH security principles:
Use SSH key authentication instead of relying exclusively on passwords.
Avoid unnecessary remote access.
Monitor authentication logs for suspicious activity.
Use a firewall to restrict network exposure.
Use intrusion-prevention tools such as Fail2ban.
Avoid performing routine administration directly as root.
Current Status
The VPS can be remotely administered through SSH, and SSH authentication and logging have been investigated as part of the security laboratory.
Further hardening is planned, including:
Creating a dedicated administrative user
Verifying SSH key-only access
Disabling unnecessary password-based authentication
Restricting direct root login
