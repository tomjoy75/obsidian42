## Terminal

Désigne une machine physique dotée de périphériques d'entrée-sortie, située à l'extrémité d'un réseau informatique.
## Console

À l'origine, elle remplace le téléscripteur. On l'appelait pupitre de commande ou console système.
Par extension, le terme "console" désigne l'appareil, et "terminal" le logiciel à l'intérieur de cette console.
## Émulateur de terminal

Le "terminal" est en réalité un **émulateur de terminal**, c'est à dire une simulation de terminal physique sous la forme d'une fenêtre. Sur les systèmes UNIX, ce terminal virtuel s'appelle "TTY". On peut l'ouvrir avec ` ctrl + alt + T `. 
Sa seule fonction est de récupérer l'entrée, et d'afficher la sortie, à travers le système des files descriptors.
Pour pouvoir traiter les commandes, on à besoin d'un autre programme, le shell
## Le shell

Un système d'exploitation possède:
- une couche de bas niveau, le noyau (ou kernel)
- une couche de haut niveau, la coque (ou shell)
Pour accéder au noyau, il faut passer par la coque. Le shell est donc l'interface utilisateur du système d'exploitation.
Il existe sous deux formes :
- CLI : interface en ligne de commande
- GUI : interface graphique
Le shell interprète et traite les commandes saisies dans le terminal et lui fournit le résultat à imprimer.
La distribution principale sous UNIX est le BASH, mais il en existe d'autres comme zsh, sh, ksh...

code (quoi)](https://www.codequoi.com/difference-entre-terminal-console-et-shell/)