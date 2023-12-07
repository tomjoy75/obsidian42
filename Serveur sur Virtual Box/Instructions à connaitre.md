## Se connecter au site distant
```bash
ssh hostname@adresse_ip (-p 4242)
ssh debian@51.77.231.174 -p 4242
```
quand on travaille en local, on peux remplacer l'adresse ip par **localhost** ou l'adresse **127.0.0.1**
!Attention: Le log en tant qu'utilisateur root peut être désactivé. Se logger en tant qu'utilisateur normal.

## Voir les  partitions logiques
```bash
$ lvdisplay
$ lsblk
```
## En global
```bash
head -n 2 /etc/os-release		: Check operateur systeme
/usr/sbin/aa-status				:APParmor actif?
whoami							:check if root user
sudo chage -l **userlog**		:info password user
sudo ufw status					:Status ufw
sudo service ufw status			:idem...voir si actif
sudo ufw allow 8080				:Ajout autorisation port 8080
ufw allow 8080/tcp				:idem
sudo ufw delete <num>			:supprime autorisation du port 
sudo vim /etc/ssh/sshd_config	:Affiche port ayant config SSH
sudo service ssh status			:Check ssh
sudo groups **userlog**			:Voir les groupes du user
cat /etc/passwd | cut -d: -f1	:Liste de tous les user sur machine 
sudo adduser userlog			:Creer un utilisateur
userdel -r userlog				:Supprimer user et ses dossiers
getent group sudo				:Liste des users du groupe sudo
getent group					:Liste des groupes
sudo vim /etc/login.defs		:Regles du mdp
sudo groupadd user42			:Creation du groupe user42
groupdel user42					:Supprime groupe user42
sudo usermod -aG user42 user	:Attribue a user le groupe user42
sudo gpasswd -d user user42		:Enleve user du groupe user42
hostname						:Nom de hote
hostnamectl						:Pareil mais + de details
sudo hostnamectl set-hostname username42	:Changer hostname
sudo reboot						:Rebooter
lsblk							:Partitions
dkpg -l | grep sudo				:Statut sudo ("ii" doit etre indique)
sudo whoami						:Verifie qu on a les privilege sudo
sudo visudo						:Definit qui a le droit d utiliser sudo (dans sudoers.tmp)
#ajouter au fichier : mon_login	ALL=(ALL:ALL) ALL
//Check the /var/log/sudo doit contenir un .log
//Run a command via sudo and check it had been updated
sudo systemctl is-enabled cron	:Check si cron est actif
sudo service cron stop			:stop cron
sudo service cron start			:start cron
sudo systemctl status cron		:Check son status
sudo crontab -u root -e			:ouvre le fichier crontab 
shasum VirtualBox.vdi			:recuperer la signature
```