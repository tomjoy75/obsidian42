### change hostname
`$ sudo hostnamectl set-hostname <nouveau_hostname> `
ou éditer le fichier /etc/hostname

### montrer statut du hostname
`$ hostnamectl status`

voir [[Dictionnaire#systemd]]
### modification users
- `useradd` crée un nouvel utilisateur
- `usermod` modification paramètres de l'utilisateur :
  **-l** pour le login, **-c** pour le nom, **-g** pour les groupes (par id)
- `userdel -r` supprime l'utilisateur et ses fichiers
- `id -u` affiche id
- `users` liste de tous les users connectes
- `cat /etc/passwd | cut -d ":" -f 1` affiche la liste de tous les users sur la machine 
- `cat /etc/passwd | awk -F '{print $1}'` idem
### manipulation des groupes
- `groupadd` crée un nouveau groupe
- `gpasswd -a` ajoute un utilisateur au groupe
- `gpasswd -d` enlève un utilisateur au groupe
- `groupdel` supprime un groupe
- `groups` affiche les groupes de l'utilisateur
- `id -g` montre l'id du groupe principal d'un utilisateur
- `getent group` affiche la liste des utilisateurs d'un groupe