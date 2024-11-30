**Keep In Mind Notes**
*  This is for the XK0-006
* [Comptia Linux+ XK0-006 Exam Objectives Bata PDF](https://comptiacdn.azureedge.net/webcontent/docs/default-source/exam-objectives/under-development/draft-linux-xk0-006-exam-objectives-(1-0).pdf?sfvrsn=a14831f9_6)
* You can buy the exam for only $50 untill the end of January 2025, book your appointment to clam the $50 deal at the COMPTIA main website.
* The objectives is to help you what you need to study for the exam. **Learn the objectives!!!**

# Domains
I added the high to low, learn what is the most important and what you don't know!
|Domain |                                              |Percentage Of Examination|
|-------|----------------------------------------------|-------------------------|
|  1.0  |                System Management             | 23% |
|  5.0  |               Troubleshooting                | 22% |
|  2.0  |          Services and User Management        | 20% |
|  3.0  |                  Security                    | 18% |
|  4.0  |   Automation, Orchestration, and Scripting   | 17% |

# Sub-Doamins
|   |                                1.0 System Management                               |
|---|------------------------------------------------------------------------------------|
|1.1|                            Explain basic Linux concepts                            |
|1.2|                 Summarize Linux device management concepts and tools               |
|1.3|                  Given a scenario, manage storage in a Linux system                |
|1.4|   Given a scenario, manage network services and configurations on a Linux server   |
|1.5|        Given a scenario, manage a Linux system using common shell operations       |
|1.6|     Given a scenario, perform backup and restore operations for a Linux server     |
|1.7|                      Summarize virtualization on Linux systems                     |

|   |                        2.0 Services and User Management                     |
|---|-----------------------------------------------------------------------------|
|2.1|       Given a scenario, manage files and directories on a Linux system      |
|2.2|   Given a scenario, perform local account management in a Linux environment |
|2.3|     Given a scenario, manage processes and jobs in a Linux environment      |
|2.4|    Given a scenario, configure and manage software in a Linux environment   |
|2.5|                  Given a scenario, manage Linux using systemd               |
|2.6|    Given a scenario, manage applications in a container on a Linux server   |

|   |                                      3.0 Security                                     |
|---|---------------------------------------------------------------------------------------|
|3.1|             Summarize authorization, authentication, and accounting methods           |
|3.2|         Given a scenario, configure and implement firewalls on a Linux system         |
|3.3|  Given a scenario, apply operating system (OS) hardening techniques on a Linux system |
|3.4|                Explain account hardening techniques and best practices                |
|3.5|        Explain cryptographic concepts and technologies in a Linux environment         |
|3.6|                Explain the importance of compliance and audit procedures              |

## 1.1 Explain basic Linux concepts
**Software licensing**
* **Resources**
    * [Why I Recommend the GPL License](https://youtu.be/zzmNA2iySEs?si=ywf7RY9GzJljCNZu)
* **Opensource software**
* **Free software**
    * GPLv3<br>
        [A Quick Guide to GPLv3](https://www.gnu.org/licenses/quick-guide-gplv3.html)<br>
        The Foundations of the GPL<br>
        Nobody should be restricted by the software they use. There are four freedoms that every user should have:
        * the freedom to use the software for any purpose,
        * the freedom to change the software to suit your needs,
        * the freedom to share the software with your friends and neighbors, and
        * the freedom to share the changes you make.<br>
        
        When a program offers users all of these freedoms, we call it free software.
* **Proprietary software**<br>
The opposite of copyleft.
    * Apache
    * BSD
    * MIT
* **Copyleft**<br>
Copyleft is the opposite of copyright.
    * GPLv3
    * LGPLv3
    * AGPLv3

## 1.2 Summarize Linux device management concepts and tools

## 1.3 Given a scenario, manage storage in a Linux system

## 1.4 Given a scenario, manage network services and configurations on a Linux server
**Network configuration**
* /etc/hosts
* /etc/resolv.conf
* /etc/nsswitch.conf

**NetworkManager**
* nmcli
* nmconnect

**Netplan**<br>
Does not replaces NetworkManager or systemd, it work with them.
* netplan apply
* netplan status
* netplan try
    * Configuration files
        * /etc/netplan

**Common network tools**
* arp
* curl
* dig
* ethtool
* hostname
* ip
    * ip address
    * ip link
    * ip route
* iperf3
* mtr
* nc
* nmap
* nslookup
* ping/ping6
* ss
* tcpdump
* tracepath
* traceroute

**Resources**
* [How to Use NetPlan in Ubuntu 18.04](https://www.youtube.com/watch?v=HlOY1ucz_DY)

## 1.5 Given a scenario, manage a Linux system using common shell operations

## 1.6 Given a scenario, perform backup and restore operations for a Linux server
**Archiving**
* cpio
* tar

**Compression tools**
* 7-Zip
* bzip2
* gzip
* unzip
* xz

**Other tools**
* **dd** | Copy & Convert<br>
Make sure to double check The Sources & Destination Before Running The Command.
```sh
dd if=/dev/READ_FROM_FILE of=/dev/WRITE_TO_FILE status=progress 

# You can create a backup IMG file and archive theme
dd if=/dev/nvme1n1p3 of=/mnt/back_up.img status=progress

# You can write the partition with the backup
dd if=/mnt/back_up.img of=/dev/nvme1n1p3 status=progress
```
* ddrescue
* **rsync**<br>
Create backup.sh filw with nano
```
nano backup.sh
```
Add, ...
```sh
#!/bin/bash

DATE=$(date '+6F')

rsync -avz /mnt/BACKUP_THIS_DATA USER@IPv4:/mnt/BACKEDUP_DATA/COOL_NAME_FOR_NEW_DATA_FOLDER/$DATE
```
Give it Executable Permissions
```
chmod +x backup.sh
```
Copy all files but "/home/Skip1/* /home/Skip2/* /home/Skip3/*" from /home to /media/Backup folder
```sh
rsync -aAXv --delete --exclude={/home/Skip1/* /home/Skip2/* /home/Skip3/*} /home /media/Backup
```
* zcat
* zgrep
* zless

**Resources**
* [Backing up a Linux Server with rsync](https://youtu.be/GqSxR93xK6E?si=tyzNl0QPZZ9TSK-T)
* [Rsync Backup on Linux](https://youtu.be/OEfboN-Nb2s?si=y9Hpqzd7SHv60qq3)
* [DD tutorial - how to clone, backup and restore disks and partitions](https://www.youtube.com/watch?v=UcF4JoFqd9E&t=423s)

## 1.7 Summarize virtualization on Linux systems