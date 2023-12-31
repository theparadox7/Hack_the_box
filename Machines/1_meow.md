# Meow Write-up

**Prepared by: Paradox**

## Setting Up

Welcome to Hack The Box! Before diving into your first vulnerable machine, make sure you are connected to the target's network. You can use either Pwnbox or a VPN configuration file.

### Pwnbox:

Running Pwnbox is straightforward. If you choose this option, no additional steps are needed.

### VPN Configuration:

1. Download the VPN (.ovpn) configuration file.
2. Open a terminal window.
3. Navigate to the Downloads folder: `cd Downloads`
4. Check if the .ovpn file is present: `ls`
5. Launch OpenVPN: `sudo openvpn {filename}.ovpn` (replace `{filename}` with your file's name)
6. Input your super-user password.

Ensure the Initialization Sequence Completed message appears.

## Introduction

The initial step in penetration testing is Enumeration, understanding the target's current state. As you're on the same VPN as the target, access it like any user. Use `nmap` to scan open ports, revealing services and potential vulnerabilities.

## Enumeration

1. Ping the target's IP: `ping {target_IP}`
2. After success, cancel ping with `CTRL+C`.
3. Scan open ports with nmap: `nmap -sV {target_IP}`

Identify open ports and services. If telnet is found, research it. Authenticate with found credentials.

## Foothold

Attempt common usernames with blank passwords:

```bash
telnet {target_IP}
Username: admin
Password: [Enter]

Username: administrator
Password: [Enter]

Username: root
Password: [Enter]

hacker


If successful, explore the directory using ls. Look for the flag.txt file. Read it with cat:
cat flag.txt


Copy the flag and paste it on the Starting Point lab's page to complete the task.


        --The Unknown Paradox
Feel free to adapt this format as needed for your GitHub repository.
