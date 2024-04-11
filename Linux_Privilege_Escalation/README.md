# Linux Privilege Escalation
-----------------------------------------------------------------------------------------------



## Enumeration
-----------------------------------------------------------------------------------------------
OS Version: 
Kernel Version: 
Running Services:



	List Current Processes
		ps aux | grep root
		ps au
	Home Directory Contents
	SSH Directory Contents
	Bash History
	Sudo - List User's Privileges
	Passwd and shadow file
	Cron Jobs - **ls -la /etc/cron.daily/**
	File Systems & Additional Drives - **lsblk**
	Find Writable Directories - **find / -path /proc -prune -o -type d -perm -o+w 2>/dev/null**
	Find Writable Files - **find / -path /proc -prune -o -type f -perm -o+w 2>/dev/null**

-----------------------------------------------------------------------------------------------


## Environment Enumeration
-----------------------------------------------------------------------------------------------

	**cat /etc/os-release**
	**echo $PATH**
	**env**
	**uname -a** 
	**lscpu**
	**cat /etc/shells**
	**cat /etc/fstab**
	**route**
	**arp -a**
	**cat /etc/passwd**
	**cat /etc/passwd | cut -f1 -d:**
	**grep "*sh$" /etc/passwd**
	**cat /etc/group**
	**getent group sudo**
	**ls /home**
	**df -h** - Mounted File Systems
	**cat /etc/fstab | grep -v "#" | column -t** - Unmounted File Systems
	**find / -type f -name ".*" -exec ls -l {} \; 2>/dev/null | grep htb-student** - All Hidden Files
	**find / -type d -name ".*" -ls 2>/dev/null** - All Hidden Directories
	**ls -l /tmp /var/tmp /dev/shm** - Temporary Files

-----------------------------------------------------------------------------------------------



## Linux Services & Internals Enumeration
-----------------------------------------------------------------------------------------------




## Credential Hunting
-----------------------------------------------------------------------------------------------

	**cat wp-config.php | grep 'DB_USER\|DB_PASSWORD'** - wordpress config file
	**find / ! -path "*/proc/*" -iname "*config*" -type f 2>/dev/null** - any config files

-----------------------------------------------------------------------------------------------




## Path Abuse
-----------------------------------------------------------------------------------------------

	**echo $PATH**
	**pwd && conncheck**
	**PATH=.:${PATH}** **export PATH** **echo $PATH**
	**touch ls** **echo 'echo "PATH ABUSE!!"' > ls** **chmod +x ls**
	**ls**


## Wildcard Abuse
-----------------------------------------------------------------------------------------------

	

## Escaping Restricted Shells
-----------------------------------------------------------------------------------------------




