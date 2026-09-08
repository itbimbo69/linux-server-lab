

A firewall controls incoming and outgoing network traffic.

During this lab I configured UFW (Uncomplicated Firewall) to control access to
the Linux server.

I checked the firewall status by using bash:

ufw status

and then enabled UFW with:
ufw enable

I configured the default policies:
ufw default deny incoming
ufw default allow outgoing

I allowed SSH access through port 22:
ufw allow 22/tcp

I checked the firewall status again:
ufw status
The final configuration blocks incoming connections by default while allowing outgoing connections and SSH access through port 22.

Logging
UFW logging was enabled with the default low logging level.
The firewall status showed:
Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing)
