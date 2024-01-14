2 Modes permettent de formater le texte dans une console ([[Formater le texte avec ANSI]])
- Les séquences d'échappement ANSI
- la commande tput
## Les séquences d'échappement

Une séquence d'échappement ANSI commence toujours avec un caractère d'échappement qui s'écrit :
```bash
\e
\033
\x1B
```
soit le 27 <sup>eme</sup> caractere ASCII nommé ESC
La structure complète d'une structure de contrôle :
`"\e" + "[" + <nombres séparés de ";" (opt.)> + <lettre>`
Par exemple, pour la séquence `\e[1;42m`
```
\e[		# appel de fonction
1;42	# paramètres de la fonction
m		# nom de la fonction
```

## La commande tput



[code quoi](https://www.codequoi.com/colorer-le-texte-du-terminal-tput-et-sequences-ansi/)