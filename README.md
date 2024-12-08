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
## 1.0 System Management
|   |                                1.0 System Management                               |
|---|------------------------------------------------------------------------------------|
|1.1|                            Explain basic Linux concepts                            |
|1.2|                 Summarize Linux device management concepts and tools               |
|1.3|                  Given a scenario, manage storage in a Linux system                |
|1.4|   Given a scenario, manage network services and configurations on a Linux server   |
|1.5|        Given a scenario, manage a Linux system using common shell operations       |
|1.6|     Given a scenario, perform backup and restore operations for a Linux server     |
|1.7|                      Summarize virtualization on Linux systems                     |
### 1.1 Explain basic Linux concepts
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
### 1.2 Summarize Linux device management concepts and tools
### 1.3 Given a scenario, manage storage in a Linux system
### 1.4 Given a scenario, manage network services and configurations on a Linux server
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
### 1.5 Given a scenario, manage a Linux system using common shell operations
### 1.6 Given a scenario, perform backup and restore operations for a Linux server
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
### 1.7 Summarize virtualization on Linux systems
**Linux hypervisors**
* Quick Emulator (QEMU)
* Kernel-based Virtual Machine (KVM)

**Virtual machines (VMs)**
* Paravirtualized drivers
* VirtIO
* Disk image operations
    * Convert
    * Resize
    * Image properties
* VM states
* Nested virtualization

**VM operations**
* Resources
    * Storage
    * RAM
    * Central processing unit (CPU)
    * Network
* Baseline image templates
* Cloning
* Migrations
* Snapshots

**Bare metal vs. virtual machines**

**Network types**
* Bridged
* Network address translation (NAT)
* Host-only/isolated
* Routed
* Open

**Virtual machine tools**
* **libvirt Application Programming Interface (API)**
    * You can use tools for example **virsh**, **virt-manager**, **virt-install**, & **virt-viewer** to interact with libvirt API.
    * Provides the software building blocks for developers to write their own virtualization solutions.
    * Several hypervisors, including VMware ESXi, KVM, and QEMU, are all built using libvirt. It provides a solid foundation for Linux-based virtualization.
    * 
* virsh
    * Is an user/client tool
* virt-manager
    * Is an user/client tool
* virt-install
    * Is an user/client tool
* virt-viewer
    * Is an user/client tool

| user/client tools  |   API   ||
|--------------------|---------|---|
|     virsh (GUI)    |||
| virt-manager (CLI) |||
| virt-install (CLI) | libvirt | Machine Emulator |
|  virt-viewer (CLI) |||
|||

**Resources**
*

## 2.0 Services and User Management
|   |                        2.0 Services and User Management                     |
|---|-----------------------------------------------------------------------------|
|2.1|       Given a scenario, manage files and directories on a Linux system      |
|2.2|   Given a scenario, perform local account management in a Linux environment |
|2.3|     Given a scenario, manage processes and jobs in a Linux environment      |
|2.4|    Given a scenario, configure and manage software in a Linux environment   |
|2.5|                  Given a scenario, manage Linux using systemd               |
|2.6|    Given a scenario, manage applications in a container on a Linux server   |
### 2.1 Given a scenario, manage files and directories on a Linux system
**Utilities**
* cd
* cp
* diff
* file
* find
* ln
* locate
* ls
* lsof
* mkdir
* mv
* pwd
* rm
* rmdir
* sdiff
* stat
* touch

**Links**<br>
There are two tyes of links `Hard links` & `Symbolic links (soft)`. `ext2`, `ext3`, `ext4`, and `XFS` file systems all support hard and Symbolic links.
* **Symbolic link**
* **Hard link**

**Device types in /dev**<br>
**Identify Block, Character, and Special Devices**<br>
 With the command `ls`, execute `ls -l /dev`. On the left side, the permissions field. The letter `c` is a **character device** or a **special file**, `b` is a **block deivce**.
```sh
# This is a M.2 device, This is an example of a Block device.
brw-rw----   1 root       disk      259,     0 Dec  7 23:27 nvme1n1
```
A way to get data in and out of your linux system. This is how your linux system communicates.
* **Block devices**<br>
Processes Input/Output in blocks and can be mounted. A block device uses buffers and caches to make transfers of large amounts of data faster. Any file storage devices are going to be block devices.
    * Storage devices, Hard Drives.
        * Data is moved in blocks, and the device can be mounted as a storage area, Information may be cached.
    * Partitions
* **Character devices**<br>
Processes Input/Output on a per-character basis
A character device is one character at a time, for example any characters a stream of data going in or out very quicky.
    * Keyboards, Deal with data on a per-byte or character level.
    * Mouse
    * Serial Port
* **Special character devices**<br>
    * The `/dev/null`, `/dev/zero`, and `/dev/urandom` files are known as special device files.
    * With the grep command and with the -e extended option `ls -l /dev | grep --color -e null -e zero -e urandom`. you can see that they are character special files.
        ```sh
        crw-rw-rw-   1 root       root        1,     3 Dec  7 23:27 null
        crw-rw-rw-   1 root       root        1,     9 Dec  7 23:27 urandom
        crw-rw-rw-   1 root       root        1,     5 Dec  7 23:27 zero
        ```
    * The `/dev/null` file
        * 
    * The `/dev/zero` file<br>
    Filling storage capacity. For example, a sysadmin can create a file of a specified size as part of testing. 
        * To create a one MiB file, <br>`dd if=/dev/zero of=FILE_NAME.txt count=1024 bs=1024`.
            * `if=FILE`, Read from FILE insted of stdin.
            * `of=FILE`, Write to FILE insted of stdin.
    * The `/dev/urandom` file<br>
    Can create a source of random characters for example creating completely randomized passwords. This command runs on low-performing systems at the risk of consuming all available resources.
### 2.2 Given a scenario, perform local account management in a Linux environment
### 2.3 Given a scenario, manage processes and jobs in a Linux environment

| Process verification |
|----------------------|
| `/proc/<PID>` |
| atop |
| htop |
| lsof |
| mpstat |
| pidstat |
| ps |
| pstree |
| strace |
| top |



**Process ID**
* Parent Process Identification Number (PPID)
* Process Identification Number (PID)

**Process states**
* Running
* Blocked
* Sleeping
* Stopped
* Zombie

**Priority**
* nice
* renice

**Process limits**

**Job and process management**
* &
* bg
* Ctrl + c
* Ctrl + d
* Ctrl + z
* exec
* fg
* jobs
* kill
* killall
* nohup
* pkill
* Signals
    *  1 HUP
    *  9 KILL
    *  15 TERM

**Scheduling**
* anacron
* at
* crontab

**Resources**
* [Linux Crash Course - htop](https://www.youtube.com/watch?v=tU9cO9FwDx0)
### 2.4 Given a scenario, configure and manage software in a Linux environment
### 2.5 Given a scenario, manage Linux using systemd
**What is systemd?**
* It's an "init system."
* The init system is the most important process running on your server (PID 1). **You can view the PID with htop**
* It manages all services that run in the background.

**Working with Units**
* Units in systemd are resources that it's able to manage.
* Units include services, timers, mounts automounts, and more!
* A service is a type of unit.

| Systemd Unit Directories | Notes |
|--------------------------|---------------------------------------------------------|
|   `/etc/systemd/system`  |         Systemd favors more than any other.             |
|   `/run/systemd/system`  |               Store runtime systemd units               |
|   `/lib/systemd/system`  | When you install a package, the unit file will go here. |

| Systemd Units |               File Examples                    | Notes |
|---------------|------------------------------------------------|-------|
|    Services   |      `/lib/systemd/system/httpd.service`       ||
|    Timers     |  `/lib/systemd/system/systemd-sysupdate.timer` | Replaces cron |
|    Mounts     |   `/lib/systemd/system/dev-hugepages.mount`    | Making sure that someting is mounted, similar to /etc/fstab file |
|    Targets    |      `/lib/systemd/system/network.target`      ||

| Primary Sections | `/lib/systemd/system/httpd.service` |
|------------------|-------------------------------------|
|       Unit       |**Description**:<br>**After**: Focuses on a specific order, from left to right to start up the unit files before staring.|
|      Service     |**Type**:<br>**ExecStart**: What happens when the process start up<br>**ExecReload**:|
|      Install     |Not required, It will configure what happens when a unit file is enabled or disabled|

* **Timers** in systemd are similar to cron jobs: you can use them to schedule tasks.
* Systemd timers are great, but cron jobs can be more effective in some situations.
* Systemd timers are a part of system and Cron jobs are more universal.
* Compared to cron jobs, systemd timers have additional features.
* Cron jobs are faster to implement than systemd timers.
* Configuring timers, there's a bit of overlap with typical systemd commands.

**Utilities**
* hostnamectl
* resolvectl
* sysctl
* systemctl
* systemd-analyze
* systemd-blame
* systemd-resolved
* timedatectl

|    OPTIONS    |                                                 Managing unit states                                                  |     systemctl Command     |
|---------------|-----------------------------------------------------------------------------------------------------------------------|---------------------------|
| daemon-reload |                            Reloads systemd, checks for edited unit files to take affect.                              |`systemctl daemon-reload`  |
|    disable    |                                      Disable the service, won't start at boot                                         |`systemctl disable SERVICE`|
|      edit     | Edit a serivce file and it creates an override file also not editing the full file. Use --full to edit the full file. |`systemctl edit    SERVICE`|
|     enable    |                                                Enable the service at boot                                             |`systemctl enable  SERVICE`|
|      mask     |||
|     reload    |                        The process reloads it's configuration files without stoping the service                       |`systemctl reload  SERVICE`|
|    restart    |                                                  Restart the service                                                  |`systemctl restart SERVICE`|
|      start    |                                                   Start the service                                                   |`systemctl start   SERVICE`|
|     status    |                                        Check the status of a unit with systemd                                        |`systemctl status  SERVICE`|
|      stop     |                                                    Stop the service                                                   |`systemctl stop    SERVICE`|
|     unmask    |||
**Resources**
* [Systemd Explained: The Ultimate Deep Dive for Linux Users](https://www.youtube.com/watch?v=Kzpm-rGAXos&t=286s)
* [Automate Your Tasks with systemd Timers: A Step-by-Step Guide](https://www.youtube.com/watch?v=n6BuUgkZ5T0)
### 2.6 Given a scenario, manage applications in a container on a Linux server

| Runtimes |
|----------|
| runC |
| Podman |
| containerd |
| Docker |

|   Image operations ~ Docker  |          Commands        |                Notes                 |
|------------------------------|--------------------------|--------------------------------------|
|         Pulling Images       | `docker pull dock0/arch` | Downloads Docker Images From Online  |

**Image operations**
* Pulling images
* Build an image
    * Dockerfile
        * ENTRYPOINT
        * CMD
        * USER
        * FROM
* Pruning
* Tags
* Layers

**Container operations**
* Read container logs
* Map container volumes
* Start/stop containers
* Inspect containers
* Delete a container
* Run
* Exec
* Pruning
* Tags
* Environmental variables

| Container operations ~ Docker |         Command         |        Notes       |
|-------------------------------|-------------------------|--------------------|
|              Run              | `docker run IMAGE_NAME` | Runs the container |

**Volume operations**
* Create volume
* Mapping volume
* Pruning
* SELinux context
* Overlay

**Container networks**
* Create network
* Port mapping
* Pruning
* Types
    * macvlan
    * ipvlan
    * Host
    * Bridge
    * Overlay
    * None

**Privileged vs. unprivileged**

**Resources**
* [Docker Essentials](https://youtube.com/playlist?list=PLT98CRl2KxKECHltRib03tG8pyKEzwf9t&si=QROt-rx3mWprtm0Z)

## 3.0 Security
|   |                                      3.0 Security                                     |
|---|---------------------------------------------------------------------------------------|
|3.1|             Summarize authorization, authentication, and accounting methods           |
|3.2|         Given a scenario, configure and implement firewalls on a Linux system         |
|3.3|  Given a scenario, apply operating system (OS) hardening techniques on a Linux system |
|3.4|                Explain account hardening techniques and best practices                |
|3.5|        Explain cryptographic concepts and technologies in a Linux environment         |
|3.6|                Explain the importance of compliance and audit procedures              |
### 3.1 Summarize authorization, authentication, and accounting methods
* Polkit
* Pluggable Authentication Modules (PAM)
* System Security Services Daemon (SSSD)/Winbind
* realm
* Lightweight Directory Access Protocol (LDAP)
* Kerberos
* Samba
* Logging
    * journalctl
    * rsyslog
    * logrotate
    * /var/log
* System audit
    * audit.rules
    * auditd

#### Kerberos
* Network authentication protocol
* Authenticate once, trusted by the system. No need to re-authenticate.
* Mutual authentication, Client and the server only. Protects against man-in-the-middle or replay attacks.
* Kerberos as in, ...
    * **Key Distribution Center (KDC)** The user sends there password, username and other authentication information if needed. Runs on TCP/88 or UDP/88, the first head
    * **Authentication Service (AS)** It authenticates the user and provides access to the network, the second head
    * **Ticket Granting Service** Provides the user with tickets, Tickets that gain access to resources on the network. the last head

**Client Authentication**<br>
Before you can gain access to the network's resources you need to first authenticate.
* Step 1<br>
    * The client sends there logon request to the Key Distribution Center. The logon request is encrypted with the date and time on the local computer. The password hash is the key, this does not sends to the Key Distribution Center. The Key Distribution Center already has the user hased password. The password hash isn't sent across the network.
* Step 2<br>
    * The Key Distribution Center receives the encrypted package and it decrypts it with the client's hased password. Makes sure that the time frame is within the five minute pariod. This is very time sensitive. Also makes sure that everyting is legitimate and sends back a **Ticket Granting Ticket**. 
    * The Ticket Granting Ticket is a ticket that allows you to get other tickets, it's an important ticket! Contains the clients name, ip address, timestamp, and validity pariod, only good for a certain amount of time. After that, you'll have to re-authenticate to the network. Is encrypted with the Key Distribution Center's secret key, the client can't decrypt it. The client also gets an Ticket Granting Serivce (TGS) Session Key. Used to encrypt the communication

**Resources**
* [Kerberos - CompTIA Security+ SY0-401: 5.1](https://www.youtube.com/watch?v=VpBCJ8vS7T0)

#### Samba
|            Samba            |                                                                      |
|-----------------------------|----------------------------------------------------------------------|
|        **Command**          |                               Notes                                  |
|   `sudo pacman -Syu samba`  | Install [Samba ~ Arch Linux](https://wiki.archlinux.org/title/Samba) |
| `sudo systemctl status smb` |                  Check Samba Status with systemd                     |
| `sudo systemctl start smb`  |                        Start Samba with systemd                      |
|                        `sudo groupadd --system smbgroup`                        | Create the system group |
| `sudo useradd --system --no-create-home --group smbgroup -s /bin/false smbuser` | Create the system user without an home dir, add smbuser to the smbgroup system group, don't let the user smbuser to login at all. |
| `sudo chown -R smbuser:smbgroup /share` |  |

**SMB client software is available for UNIX-based systems. Samba software allows UNIX and Linux servers.**

**Configure The /etc/samba/smb.conf File**
The `/etc/samba/smb.conf` file stores Samba [configuration data](https://git.samba.org/samba.git/?p=samba.git;a=blob_plain;f=examples/smb.conf.default;hb=HEAD). Because the `samba` package does not provide this file, create the file before starting `smb.service`<br>
```sh
[global]
    server string = A Basic Description
    workgroup = NameOfBusiness   # Or anything to make it more organized.
    security  = user   # If you have a windows domain or an active directory server you can use this. User level security,  Not the best when it comes to security and it comes with some challenges. On a smaller network, its fine.
    map to guest = Bad User   # Login is not required! Add `never` if you need the user to login.
    #usershare allow guests = yes   # Allow guests
    #hosts allow = 192.168.0.0/16   # Allow anyone that starts with an IPv4 range of 192.168
    #hosts deny = 0.0.0.0/0   # Deny all users that does not start with an IPv4 range of 192.168
    name resolve order = bcast host   # Checks broadcat first then the /etc/hosts file
    include = /etc/samba/shares.conf
```

**Configure The /etc/samba/shares.conf File**<br>
This file is what folders to share.
```sh
[Public Files]   # The share name
path = /share/public_shares   # Share the folder named public_shares
#read only = no   # This makes it writeable
#guest ok = yes   # Allows guests
force user = smbuser   # Anything that is created within the folder will be owned by the `smbuser` user. Make sure the user exists in Linux, system user type.
force group = smbgroup   # Anything that is created within the folder will be owned by the `smbgroup` group. Make sure the group exists in Linux, system group type.
create mask = 0664   # Set the permissions for newly created files
force create mode = 0664
directory mask = 0775   # Newly created directories will have permission. Note, with Directories you need to have the excute bit in order to go inside of the directory.
force directory mode = 0775
public = yes
writable = yes # Allow changes
```

**Resources**
* [Setting up Simple Samba File Shares](https://www.youtube.com/watch?v=7Q0mnAT1MRg)
* [How to setup Samba for File Sharing in Linux](https://www.youtube.com/watch?v=oRHSrnQueak)
### 3.2 Given a scenario, configure and implement firewalls on a Linux system
### 3.3 Given a scenario, apply operating system (OS) hardening techniques on a Linux system
### 3.4 Explain account hardening techniques and best practices
### 3.5 Explain cryptographic concepts and technologies in a Linux environment
### 3.6 Explain the importance of compliance and audit procedures

## 4.0 Automation, Orchestration, and Scripting
|   |                         4.0 Automation, Orchestration, and Scripting                          |
|---|-----------------------------------------------------------------------------------------------|
|4.1| Summarize the use cases and techniques of automation and orchestration in a Linux environment |
|4.2|                Given a scenario, perform automated tasks using shell scripting                |
|4.3|                 Summarize Python basics used for Linux system administration                  |
|4.4|                     Given a scenario, implement version control using Git                     |
|4.5|         Summarize best practices and responsible uses of artificial intelligence (AI)         |
### 4.1 Summarize the use cases and techniques of automation and orchestration in a Linux environment
**Infrastructure as code**
    * Ansible
        * Playbooks
        * Inventory
        * Modules
        * Ad hoc
        * Collections
        * Facts
        * Agentless

**Puppet**
    * Classes
    * Certificates
    * Modules
    * Facts
    * Agent/Agentless

**OpenTofu**
* Provider
* Resource
* State
* Application programming interface (API)

**Unattended deployment**
* Kickstart
* Cloud-init

**Continuous integration/Continuous deployment (CI/CD)
* Version control
* Shift left testing
* GitOps
* Pipelines
* DevSecOps

**Deployment orchestration**
* Kubernetes
    * ConfigMaps
    * Secrets
    * Pods
    * Deployments
    * Volumes
    * Services
    * Variables
* Docker Swarm<br>
Swarm mode is an advanced feature for managing a cluster of Docker daemons
    * Service
    * Nodes
    * Tasks
    * Networks
    * Scale
* Docker/Podman Compose
    * Compose file
    * Up/down
    * Logs

**Resources**

### 4.2 Given a scenario, perform automated tasks using shell scripting
### 4.3 Summarize Python basics used for Linux system administration
### 4.4 Given a scenario, implement version control using Git
**Install git on Arch Linux**<br>
`sudo pacman -Syu git`

|        Command       |                       Note                      |
|----------------------|-------------------------------------------------|
|  `git init myrepo`   |           Initialize a blank repository         |
| `git add nameOfFile` |        Add file to the tracked files list       |
|     `git config`     | Allows to set a configuration parameter for git |
| `git config --global user.name "NAME"` | Set the name for the user |
| `git config --global user.email "name@example.com"` | Set the email address for the user |
| `git commit -m "Commit Message"` | Make Sure To Write a Very Good Message For This Commit!!! This does not send the changes to a remote server. |
|     `git commit`    | This opens an text editer insted of using the CLI to add an message. |
| `git diff FILENAME` | `+` Added line<br>`-` Removed line<br>This shows what has changed. |
| `git log --oneline` | List of commits |
| `` |  |

* .gitignore
* branch
* checkout
* clone
* fetch
* merge
    * squash
* pull
* push
* rebase
* reset
* stash
* tag

**Resources**
* [Git Essentials](https://www.youtube.com/watch?v=u1Zvkqjx0Ik)
### 4.5 Summarize best practices and responsible uses of artificial intelligence (AI)

## 5.0 Troubleshooting
|   |                          5.0 Troubleshooting                                    |
|---|---------------------------------------------------------------------------------|
|5.1|      Summarize monitoring concepts and configurations in a Linux system         |
|5.2|Given a scenario, analyze and troubleshoot hardware, storage, and Linux OS issues|
|5.3|  Given a scenario, analyze and troubleshoot networking issues on a Linux system |
|5.4|   Given a scenario, analyze and troubleshoot security issues on a Linux system  |
|5.5|           Given a scenario, analyze and troubleshoot performance issues         |
### 5.1 Summarize monitoring concepts and configurations in a Linux system

**Resources**
### 5.2 Given a scenario, analyze and troubleshoot hardware, storage, and Linux OS issues

**Resources**
### 5.3 Given a scenario, analyze and troubleshoot networking issues on a Linux system
**Common issues**
* Misconfigured firewalls
* DHCP issues
* DNS issues
* Interface misconfiguration
    * Maximum transmission unit (MTU) mismatch
    * Bonding
    * Media access control (MAC) spoofing
    * Subnet
    * Cannot ping server
* Routing issues
    * Gateway
* Server unreachable
* IP conflicts
* Dual stack issues (IPv4 and IPv6)
* Link down
* Link negotiation issues
**Resources**
### 5.4 Given a scenario, analyze and troubleshoot security issues on a Linux system
**Common issues**
* SELinux issues
    * Policy
    * Context
    * Booleans
* File and directory permission issues
    * ACLs
    * Attributes
* Account access
* Unpatched vulnerable systems
* Exposed or misconfigured services
* **Remote access issues**<br>
**What to do when a user is unable to log into a server via SSH**
    1. Try to connect to the server via SSH and if you're able to connect, then SSH is working.
    1. If this user particular user is the only one expersiancing this problem. 
        1. Try tailing the authentication logs.
            ```sh
            tail -f /var/log/auth.log   # Debian
            tail -f /var/log/errors.log   # Arch Linux
            ```
        1. Tell the user to try to log in again.
        1. After asking the user, you will see that the log file will update live, because `-f` with the command `tail` is follow mode. If the user is trying to log into the server, you'll see the error message in the log live.
* 

* Certificate issues
* Misconfigured package repository
* Use of obsolete or insecure protocols and ciphers
* Cipher negotiation issues

**Resources**
* [10 Common Linux Issues and How to Fix Them](https://www.youtube.com/watch?v=xsdFNpThetE)
### 5.5 Given a scenario, analyze and troubleshoot performance issues
**Common symptoms**
* Swapping
* Out of memory
* Slow application response
* System unresponsiveness
* High CPU usage
* High load average
* High context switching
* High failed log-in attempts
* Slow startup
* High input/output (I/O) wait time
* Packet drops
* Jitter
* Random disconnects
* Random timeouts
* High latency

**Slow response times**<br>
**Slow performance in GNOME Desktop Environment (DE)**<br>
**Tracker**: Scans files on your system to find them faster, an indexing service. Tracker will index everything, this will make the system slow. Which this makes gnome look bad but gnome is a very fast and efficient Desktop Environment (DE).
    1. Create a file `touch /mnt/truenas/archive/.trackerignore` and leave it empty. This will stop tracker from scanning that directory. Perfect for file shares unless you whant Tracker to scan that directory. The main problem is that Tracker will scan everything you have on your computer, the / root, anything that is mounted, everything. That takes time and will make gnome Desktop Environment very slow. Just create the .trackerignore file in the root of the file share that you don't what to scan.

* High disk latency
* Low throughput
* Blocked processes
* Hardware errors
* Sluggish terminal behavior
* Exceeding baselines
* Slow remote storage response
* CPU bottleneck

**Resources**
* [10 Common Linux Issues and How to Fix Them](https://www.youtube.com/watch?v=xsdFNpThetE)