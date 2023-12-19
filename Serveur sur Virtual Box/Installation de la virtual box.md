## Fonctionnement de base d’une VM

Une machine virtuelle est la réplique version software d’un ordinateur qui va héberger un système d’exploitation.(CPU, mémoire vive, ..)
Elle est constituée d’une couche appelée hypervisor entre le système d’exploitation parent, et le(s) systèmes d’exploitations enfants 
## Choix du système d’exploitation

Debian parce que plus simple à mettre en place, plus répandu sur les serveurs en général (15,6% contre 9,7 pour rocky).
## Les différences principales entre Rocky and Debian

- Debian: distribution ancienne (1993) mère de plein d’autres versions comme ubuntu. connue pour sa stabilité et son vaste catalogue de paquets, et maintenue par une communauté de bénévoles. Facile a mettre a jour. Plusieurs branches (stable, testing, unstable). Pas de version Entreprise. 
  Suit un cycle de sortie non fixe avec de nouvelles versions majeures tous les 2 ans.
   
- Rocky a été créée récemment pour être une alternative à CentOS(2004). Historiquement, Red Hat Linux était payant et on a développé une alternative gratuite. mais il y a un changement de politique sur centOS (distribution stable -> modèle de flux de sortie(Cent OS stream))  
   suit le cycle de sortie de RHEL -> stabilité long terme et maj pendant période étendue(soutien de 10 ans). principalement destiné aux entreprises et serveurs.
## Les bénéfices des machines virtuelles

Les +
- Possibilité d'expérimenter d’autres sys d’exploitations sans changer d’ordinateur, ni le partitionner
- Installer un ancien sys d’exploitation même si plus compatible avec le matériel physique
- Avoir un sys d’exploitation entier sur clé USB
- Développer un programme prévu sur un autre système d’exploitation
- Économie de dépenses, en électricité et maintenance
- Sécurité (fonctionne comme des cloisons étanches), pour l'étude des virus par exemple.

Les -

- L’ordinateur hôte doit supporter la virtualisation (RAM)
- Si l’ordinateur hôte tombe en panne, plus d'accès aux VM.
## difference between aptitude and apt, [[APPArmor]]

aptitude et apt sont deux gestionnaires de paquets.

apt, ligne de commande, plus simple d’utilisation, sortie plus prévisible pour les scripts.

aptitude, il y a une interface interactive, plus complet sur la gestion de dépendances+journal détaillé+recherche