Programme qui permet d’exécuter des scripts, des commandes ou autres, a une date ou un intervalle spécifié.
` systemctl enable cron`
cron est un daemon qui regarde régulièrement dans un tableau, la crontab, pour savoir si il y a des taches a exécuter.
`crontab -e` editer une crontab (6 colonnes)
`minutes/heures/jours du mois/mois/jour de la semaine/commande`
#### Wildcards
- `*` remplace toutes les valeurs ex: `* * * * * commande`
- `,` pour mettre plusieurs valeurs ex: `0,5,20 * * * * commande`
- `*/` par saut de tant. Par ex, toutes les 5 minutes `*/5 * * * *`
- `-`  champs de valeur. ex, du lundi au vendredi `* * * * 1-5`
#### Exemples
- Toutes les 5 minutes de la premiere demi heure de chaque heure :
  `0-25/5 * * * * commande`
- Tous les 2emes vendredi de chaque mois :
  `5 23 8-14 * 5 commande`
#### Pour les jours de la semaine:
- 0: Dimanche
- 1: Lundi 
- 2: Mardi ...
- ...6: Samedi 
- 7: Dimanche
#### Ressource 
[crontab guru](https://crontab.guru/)




