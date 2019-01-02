# toppo

Toppo Vulnhub VM walkthrough


## netdiscover

Find the IP on your subnet. The Kali VM has two NICs, one is on the host-only network with the VM.

![Alt text](./netdiscover1.png?raw=true)


## nmap

Use nmap to scan for all possible ports.

![Alt text](./nmap1.png?raw=true)

Direct the scan to the applicable ports for more info.

![Alt text](./nmap2.png?raw=true)


## dirbuster & nikto

Not much on any ports except for 80. Dirbuster and nikto show similar results. Check the directories and files.

![Alt text](./dirbuster.png?raw=true)

![Alt text](./nikto.png?raw=true)


## notes.txt vulnerable

Browse to the vulnerable file for sensitive information.

![Alt text](./notes.png?raw=true)


## low privilege shell

So after trying some basic username lists that did not work, duh, try ted with success.

![Alt text](./lowshell.png?raw=true)


## vulnerable file for privilege escaltion

The simple basics for privilege escalation (FFSACE): files, folders, services, applications, connections, exploits

Anything readable/writeable may be vulnerable. The sticky bit on the specific python version is vulnerable and can run with root privilege based on the permissions and ownership.

![Alt text](./vulnfile.png?raw=true)


## reverse shell

Craft the payload for the vulnerable binary for your configuration. Setup your listener with something like netcat.

![Alt text](./nmap.png?raw=true)


## root shell

The vulnerable binary returns with the hotness.

<html>
<pre>
\(*_*)
  ( (>
  /  \
  </pre>
</html>

![Alt text](./nmap.png?raw=true)


## get the flag

![Alt text](./nmap.png?raw=true)

## Thanks to Hadi Mene for the VM.
