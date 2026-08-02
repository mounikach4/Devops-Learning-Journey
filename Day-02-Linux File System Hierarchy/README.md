## Linux File System Hierarchy (FHS)
 * **FHS:** Filesystem Hierarchy Standard
 * Linux relies on a single **tree-like structure** starting from the Root directory (/). Unlike Windows (which uses drive letters like C:\ or D:\), every file, directory, connected device, and system process in Linux exists under this unified hierarchy.
### Linux Directory Structure:
<pre>
/ (Root Directory)
│
┌────────┬────────┬─────────┼─────────┬────────┬────────┬────────┐
│        │        │         │         │        │        │        │
▼        ▼        ▼         ▼         ▼        ▼        ▼        ▼
/bin    /sbin    /etc      /home     /root    /boot    /dev     /var
│        │        │         │         │        │        │        │
...      ...      ...       ...       ...      ...      ...      ...
</pre>
## Key Directory Breakdown
### Core System & Commands
 * **/ (Root):** The top-level directory. Everything in Linux starts from here.
 * **/bin (User Binaries):** Essential executable commands accessible by all users (e.g., ls, cp, mv, cat).
 * **/sbin (System Binaries):** Essential administrative commands required for system maintenance (e.g., reboot, fdisk, shutdown).
 * **/lib & /lib64 (System Libraries):** Shared library files required by binaries in /bin and /sbin.
### Configurations & Users
 * **/etc (Configuration Files):** Holds all system-wide configuration files and startup scripts (e.g., network settings, user account data).
 * **/home (User Home Folders):** Stores personal files and documents for standard users (e.g., /home/username).
 * **/root (Superuser Home):** The dedicated home directory for the root administrator account (separate from /).
### Storage, Devices & Booting
 * **/boot (Boot Files):** Contains bootloader files, Linux Kernel images (vmlinuz), and initrd.
 * **/dev (Device Files):** Hardware components (disks, USBs, terminals) represented as files (e.g., /dev/sda).
 * **/mnt & /media (Mount Points):**
   * **/media:** Temporary mount points for removable media (USBs, CDs).
   * **/mnt:** Manual temporary mount location for sysadmins.
### Runtime, Services & Dynamic Data
 * **/var (Variable Data):** Stores dynamic data that continuously changes, such as system logs (/var/log), mail queues, and databases.
 * **/tmp (Temporary Files):** Temporary space for applications; cleared automatically on system reboot.
 * **/srv (Service Data):** Holds site-specific data served by web servers or FTP servers.
 * **/usr (User Programs):** Contains secondary user binaries, libraries, and documentation (/usr/bin, /usr/lib).
 * **/opt (Optional Packages):** Location for installing third-party standalone software packages.
 * **/proc (Process Information):** A **virtual/pseudo filesystem** stored in RAM that provides real-time kernel metrics and process information.
### Why is this important for DevOps?
<pre>
Troubleshooting        Configuration Mgmt        Storage Management
(/var/log files) ──►   (/etc config files) ──►  (/dev & /mnt drives)
</pre>
 * **Log Analysis:** Knowing /var/log enables fast debugging during deployment or server failures.
 * **Infrastructure Automation:** Ansible and Terraform frequently interact with /etc to configure instances automatically.
 * **Cloud Volume Attachments:** Managing attached storage blocks (like AWS EBS) requires working with /dev and /mnt.
