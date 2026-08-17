Week 3 Portfolio Project

Enterprise Server Deployment and Operating System Installation

Course: ITEP 414 -- System Administration and Maintenance
Program: Bachelor of Science in Information Technology (BSIT)
Prepared by: Regie M. Estravela
Week: 3

Project Overview

This project documents the deployment of an Ubuntu Server virtual
machine for a simulated startup enterprise environment. The server was
installed, configured, secured for remote administration using SSH,
verified through standard Linux commands, and documented as part of a
professional system administration portfolio.

Learning Objectives

Install Ubuntu Server in a virtual machine using recommended
settings.

Configure hostname, user account, storage, networking, and SSH.

Verify server functionality using standard Linux commands.

Explain the difference between BIOS and UEFI.

Describe the Ubuntu boot process.

Compare Windows Server, Ubuntu Server, and Rocky Linux.

Create professional technical documentation for a server deployment.

Virtual Machine Specifications

Component          Configuration

VM Name            Ubuntu-Server-Week03
Operating System   Ubuntu Server 24.04.4 LTS
RAM                4 GB
CPU                2 virtual processors
Storage            40 GB VDI
Network            NAT / DHCP
Hostname           server01
User               regie (non-root administrative user)
SSH                OpenSSH Server

Installation Summary

Ubuntu Server 24.04.4 LTS was installed in Oracle VirtualBox. English
was selected as the installation language, DHCP was accepted for network
configuration, and the hostname was configured as server01. A non-root
administrative user was created. Guided -- Use Entire Disk was selected
for the 40 GB virtual disk, and OpenSSH Server was enabled for secure
remote administration. No additional snaps were selected. After
installation, the Ubuntu installation ISO was removed before rebooting.

Configuration Summary

The server was configured with the required hostname, administrative
user account, 40 GB virtual storage, DHCP networking, and OpenSSH
Server. The system was updated using:

sudo apt update
sudo apt upgrade -y

The SSH service was verified and displayed active (running).

Verification Results

The following required verification tasks were completed:

hostname --- confirmed server01.

ip addr --- displayed the DHCP-assigned IPv4 address.

ping -c 4 google.com --- returned successful replies with 0%
packet loss.

systemctl status ssh --- showed the SSH service as
active (running).

Screenshots for these four verification tasks are stored in the
screenshots/ folder.

BIOS vs UEFI Highlights

BIOS is legacy firmware commonly associated with MBR-based booting and
traditional storage limitations. UEFI is the modern firmware interface
and works with GPT, supports much larger storage devices, and provides
modern security capabilities such as Secure Boot. UEFI has largely
replaced BIOS because modern computers require larger storage, stronger
security, and more flexible boot management.

A complete comparison is provided in BIOS_vs_UEFI.pdf.

Ubuntu Boot Process Flowchart

The Ubuntu boot process documented for this project is:

Power On → BIOS/UEFI Initialization → Boot Device Detection → Boot
Loader (GRUB) → Linux Kernel → init/systemd → Services Start → Login
Prompt

The flowchart files are stored in the diagrams/ folder.

Windows Server Evaluation

A separate Windows Server Evaluation virtual machine was installed for
the bring-home activity. An Administrator password was configured,
successful login was completed, and the computer name was configured as
WIN-SERVER-WEEK03. Screenshots documenting the Windows Server
installation and configuration are included in the screenshots/ folder
and the Installation Guide.

Operating System Comparison

Category          Windows Server            Ubuntu Server     Rocky Linux

Licensing         Proprietary/commercial;   Open-source with  Open-source enterprise
evaluation editions       optional          Linux distribution
available                 commercial
support

User Interface    GUI and command-line      Primarily         Primarily command-line
administration            command-line for  for server
server            installations
installations

Package           Windows Update and        APT / dpkg        DNF / RPM
Management        Windows
package-management tools

Security          Active Directory, Group   Linux             SELinux, Linux
Policy, Defender,         permissions,      permissions,
security baselines        sudo, SSH,        firewalld, SSH
firewall tools,
AppArmor

Performance       Strong for Microsoft      Efficient and     Stable platform for
workloads and enterprise  flexible for web, enterprise Linux
services                  cloud, databases, workloads
and
infrastructure

Typical           Active Directory,         Web servers,      Enterprise Linux
Enterprise Use    Microsoft services,       cloud, databases, servers and
Windows applications,     containers,       RHEL-compatible
file services             internal services workloads

Advantages        Excellent Microsoft       Free, flexible,   Stable,
ecosystem integration and broad community   enterprise-oriented,
centralized management    and software      RHEL-compatible
ecosystem

Challenges Encountered

The Ubuntu installer remained at Reading package lists during
installation.

The archive mirror was adjusted to allow the installation to
continue.

The virtual machine returned to the installer after installation
because the installation media needed to be removed.

The Ubuntu hostname initially required correction to match the
module requirement.

SSH status required verification until it displayed
active (running).

Reflection

Completing the Week 3 project gave me practical experience in deploying
and maintaining an operating system in a virtualized environment. I
learned that server installation is not only about getting the operating
system to start, but also about properly configuring the hostname, user
account, storage, networking, and remote administration services. Using
Oracle VirtualBox allowed me to practice these tasks without affecting a
physical computer.

One of the most useful parts of the activity was server verification.
Commands such as hostname, ip addr, ping -c 4 google.com, and
systemctl status ssh provided direct evidence that the server was
configured and functioning correctly. I also learned the importance of
documenting each step with screenshots because technical documentation
should allow another administrator to understand and reproduce the
deployment.

The installation process also exposed me to real troubleshooting
situations. The Ubuntu installer remained at "Reading package lists,"
and the virtual machine later returned to the installer after
installation. These problems helped me understand the importance of
checking the archive mirror and removing installation media before
rebooting. I also gained experience installing Windows Server Evaluation
in a separate virtual machine and configuring its computer name.

The BIOS and UEFI comparison helped me understand how modern computers
start their operating systems and why UEFI is now commonly used.
Overall, this project strengthened my understanding of virtualization,
Linux server administration, SSH, system verification, troubleshooting,
and professional technical documentation. These are useful foundational
skills for future system administration and infrastructure work.

References

Ubuntu Server Documentation ---
https://documentation.ubuntu.com/server/

UEFI Forum --- https://uefi.org/

Microsoft Learn --- https://learn.microsoft.com/

Rocky Linux Documentation --- https://docs.rockylinux.org/
