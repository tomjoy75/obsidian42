## Instructions utiles
- [[awk]]
- [conditions dans un script](https://buzut.net/maitriser-les-conditions-en-bash/)
## Ou trouver l'info
- `uname` : architecture information
- `/proc/cpuinfo` : CPU information
- `free` : RAM information
- `df` : disk information (`df -total`)
- `top -bn1` : process information
- `who -b` : boot and connected user information
- `lsblk` : partition and LVM information
- `/proc/net/sockstat` : TCP information
- `ss -t` : affiche les sockets TCP
- `who` : info on users actually logged in
- `hostname -I` : hostname and IP information
- `ip link show` / `ip address` : IP and MAC information
## Configuration du script
- **architecture du système d'exploitation**
  `uname -a` Affiche les informations système
- **nombre de processeurs physiques et virtuels**
  On trouve ces infos dans */proc/cpuinfo* aux lignes "physical id" et "processor"
- **mémoire vive et mémoire disponible ainsi que taux d'utilisation en %**
  Pour la mémoire vive, voir la fonction `free --mega`
-
## Script
```bash
#!/bin/bash

archi=$(uname -a)
phcpu=$(grep "physical id" /proc/cpuinfo | wc -l)
vicpu=$(grep "processor" /proc/cpuinfo | wc -l)
#RAM
mem_usage=$(free --mega | awk '$1 == "Mem:" {print $3}')
mem_total=$(free --mega | awk '$1 == "Mem:" {print $2}')
mem_percent=$(free | awk '$1 == "Mem:" {printf("%.2f%%\n", $3*100/$2)}')
#Memory
disk_usage=$(df --total | awk '$1 == "total" {print int($3/1024)}')
disk_total=$(df --total | awk '$1 == "total" {print int($2/1048576)}')
disk_percent=$(df --total | awk '$1 == "total" {print $5}')
#Processor
proc_usage=$(top -bn1 | awk '$1 == "%Cpu(s):" {printf("%.1f\n", $2+$4)}')
#Boot
b_date=$(who -b | awk '{print $3}')
b_time=$(who -b | awk '{print $4}')
#LVM
lvm=$( (( $(lsblk | grep "lvm" | wc -l) > 0 )) && echo yes || echo no )
#Number of actives connections
tcp=$(ss -t| grep ESTAB | wc -l)
#Users logged in
users=$(who | wc -l)
#Addresses
ipv4_addr=$(hostname -I)
mac_addr=$(ip link show | awk '$1 == "link/ether" {print $2}')

wall "	#Architecture: $archi
	#CPU physical : $phcpu
	#vCPU : $vicpu
	#Memory Usage: $mem_usage/${mem_total}MB ($mem_percent)
	#Disk Usage: $disk_usage/${disk_total}Gb ($disk_percent)
	#CPU load: $proc_usage%
	#Last boot: ${b_date} ${b_time}
	#LVM use: $lvm
	#Connexions TCP : $tcp ESTABLISHED
	#User log: $users
	#Network: IP $ipv4_addr($mac_addr)
	#Sudo : $nb_cmd cmd
"
```