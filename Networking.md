 Networking is a fundamental part of Linux server administration.

During this lab I explored the basic concepts of how devices communicate with
a publicly accessible Linux server.

## IP Addresses

An IP address identifies a device on a network.

The VPS has a public IP address that allows it to be reached from the Internet.

For documentation, server IP addresses are represented using:

`SERVER_IP`

## Ports

A port identifies a specific network service running on a host.

One server can run multiple services on different ports.

Examples:

- Port 22 — SSH
- Port 80 — HTTP

## TCP and UDP

TCP and UDP are transport-layer protocols.

### TCP

TCP is connection-oriented and provides reliable data delivery.

SSH and HTTP commonly use TCP.

### UDP

UDP is connectionless and does not guarantee delivery.

It has lower overhead and is useful when speed is important.

## Localhost

`127.0.0.1` is the IPv4 loopback address.

It refers to the local machine.

The hostname `localhost` normally refers to the same address.

A service listening only on `127.0.0.1` is generally not accessible from the
Internet.

## 0.0.0.0

`0.0.0.0` means that a service listens on all available IPv4 interfaces.

This is different from `127.0.0.1`, which refers only to the local machine.

## DNS

DNS (Domain Name System) translates domain names into IP addresses.

For instance:
whatever.com → SERVER_IP
