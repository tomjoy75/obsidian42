## infos liées a l'age du mdp

dans le repertoire /etc/login.defs
pour afficher ou changer la politique du mdp pour un user, on peux utiliser chage
`chage -l username` voir les infos
`chage username`changer les infos

## infos liees au format du mdp

La config se fait en general au sein du module PAM(Pluggable Authentification Module)
/etc/pam.d/common-password
