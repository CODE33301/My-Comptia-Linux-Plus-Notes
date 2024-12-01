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

## 1.0 System Management
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

## 3.0 Security
|   |                                      3.0 Security                                     |
|---|---------------------------------------------------------------------------------------|
|3.1|             Summarize authorization, authentication, and accounting methods           |
|3.2|         Given a scenario, configure and implement firewalls on a Linux system         |
|3.3|  Given a scenario, apply operating system (OS) hardening techniques on a Linux system |
|3.4|                Explain account hardening techniques and best practices                |
|3.5|        Explain cryptographic concepts and technologies in a Linux environment         |
|3.6|                Explain the importance of compliance and audit procedures              |

## 4.0 Automation, Orchestration, and Scripting
|   |                         4.0 Automation, Orchestration, and Scripting                          |
|---|-----------------------------------------------------------------------------------------------|
|4.1| Summarize the use cases and techniques of automation and orchestration in a Linux environment |
|4.2|                Given a scenario, perform automated tasks using shell scripting                |
|4.3|                 Summarize Python basics used for Linux system administration                  |
|4.4|                     Given a scenario, implement version control using Git                     |
|4.5|         Summarize best practices and responsible uses of artificial intelligence (AI)         |

## 5.0 Troubleshooting
|   |                          5.0 Troubleshooting                                    |
|---|---------------------------------------------------------------------------------|
|5.1|      Summarize monitoring concepts and configurations in a Linux system         |
|5.2|Given a scenario, analyze and troubleshoot hardware, storage, and Linux OS issues|
|5.3|  Given a scenario, analyze and troubleshoot networking issues on a Linux system |
|5.4|   Given a scenario, analyze and troubleshoot security issues on a Linux system  |
|5.5|           Given a scenario, analyze and troubleshoot performance issues         |