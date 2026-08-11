# linux-server-lab
Personal Linux server lab – practicing SSH, networking,firewall,Docker, Nginx and server administration
Linux Server & Security Lab

A hands-on Linux server environment focused on system administration, networking, security monitoring, and DevOps fundamentals.

Overview

This project documents the deployment and administration of an internet-facing Linux server.

The lab is used to explore real-world server operations, including SSH administration, network exposure, authentication logs, firewall configuration, containerization, and automated security monitoring.

Security Monitoring

The server is monitored for unsolicited internet traffic and automated activity, including:

- SSH connection attempts
- Failed authentication attempts
- Source IP addresses
- Attempted usernames
- Repeated connection attempts
- Network scanning activity

The collected data is used to understand common background activity targeting publicly accessible servers and to evaluate basic defensive measures.

Technology Stack

- Linux
- SSH
- Git
- Docker
- Nginx
- Firewall
- Fail2ban
- Log analysis
- Monitoring

Objectives

- Develop practical Linux administration skills
- Understand networking and server exposure
- Implement basic server hardening
- Analyze authentication and system logs
- Detect and respond to suspicious activity
- Deploy containerized services
- Document infrastructure and configuration changes

Progress

- [x] Deploy and access the server via SSH
- [ ] Create a dedicated administrative user
- [ ] Configure SSH key authentication
- [ ] Configure firewall rules
- [ ] Analyze SSH authentication logs
- [ ] Implement intrusion prevention
- [ ] Deploy Docker containers
- [ ] Configure Nginx as a reverse proxy
- [ ] Configure DNS and HTTPS
- [ ] Implement monitoring and alerting
- [ ] Build a security monitoring dashboard
- [ ] Configure automated backups

Disclaimer

This is a personal educational laboratory. All systems and infrastructure monitored or administered as part of this project are owned by me or used with appropriate authorization.
