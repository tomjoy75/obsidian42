## Instructions utiles
- [[awk]]
## Ou trouver l'info
- `uname` : architecture information
- `/proc/cpuinfo` : CPU information
- `free` : RAM information
- `df` : disk information (`df -total`)
- `top -bn1` : process information
- `who` : boot and connected user information
- `lsblk` : partition and LVM information
- `/proc/net/sockstat` : TCP information
- `hostname` : hostname and IP information
- `ip link show` / `ip address` : IP and MAC information
## Configuration du script
- **architecture du système d'exploitation**
  `uname -a` Affiche les informations système
- **nombre de processeurs physiques et virtuels**
  On trouve ces infos dans */proc/cpuinfo* aux lignes "physical id" et "processor"
- **mémoire vive et mémoire disponible ainsi que taux d'utilisation en %**
  Pour la mémoire vive, voir la fonction `free --mega`
- 