#### Quelques commandes de base
- `exit ou logout` : termine la session
- `su autre_login` : **su** (switch user) pour changer d'utilisateur. On en sort avec **exit**
- `systemctl reboot`: redémarre le système (root requis)
- `systemctl poweroff`: éteint le système

## Pour voir les volumes physiques et logiques
En mode root
- `pvs` : List physical volumes in LVM Group
- `vgs` : List volume groups in LVM Group
- `lvs` : List logical volumes in LVM Group