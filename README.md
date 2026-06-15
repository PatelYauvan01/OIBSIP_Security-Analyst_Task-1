# Network Scan Findings

## Overview

This document contains the analysis of Nmap scan results performed on the target host.

## Target Information

| Field | Details |
|---|---|
| Host | RTK_GW.bbrouter |
| IP Address | 192.168.1.1 |
| Status | Host is up |
| MAC Vendor | OVT India pvt |
| Network Distance | 1 hop |

## Open Ports Summary

| Port | Service | Status | Significance |
|---|---|---|---|
| 21/tcp | FTP | Open | File Transfer Protocol is used to transfer files between systems. If not secured, FTP can expose usernames, passwords, or sensitive files because standard FTP sends data in plain text. |
| 23/tcp | Telnet | Open | Provides remote command-line access. Telnet traffic is unencrypted, making it vulnerable to credential interception. Secure alternatives like SSH are preferred. |
| 53/tcp | DNS | Open | Domain Name System service translates domain names into IP addresses. Open DNS services should be properly configured to prevent information leakage or DNS abuse. |
| 80/tcp | HTTP | Open | Hosts a web interface or website over an unencrypted connection. Router administration panels commonly use this port, but sensitive access should use HTTPS. |
| 443/tcp | HTTPS | Open | Provides encrypted web communication using SSL/TLS. Commonly used for secure router management or web services. |
| 445/tcp | Microsoft-DS/SMB | Open | Used for file sharing and network communication. If exposed or misconfigured, SMB can become a security risk due to unauthorized access or known vulnerabilities. |

## Security Observations

- FTP and Telnet are considered risky because they transmit information without encryption.
- HTTPS is preferred over HTTP for secure administration.
- SMB access should be restricted only to trusted devices.
- Unnecessary open ports should be disabled to reduce attack surface.
- Strong authentication and updated firmware should be maintained.

## Conclusion

The scan discovered six open TCP ports on the host. These services provide functionality such as file transfer, web management, DNS resolution, and file sharing. However, services like FTP, Telnet, and SMB require careful configuration because they may introduce security vulnerabilities if left exposed.

