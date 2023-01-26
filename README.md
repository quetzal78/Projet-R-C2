# Projet-R&C2  
  ###### Projet - Bachelor Cybersécurité et Réseaux Argenteuil - Thème Hardening: Protocole de couche 3 et 4  

## Introduction  

  ### Définition des Parties
   Qu'est-ce que le SSH ?  
   Qu'est-ce que ...  
  
  ### Ouverture sur tout les problèmes liés aux couches 3 et 4
   Comment sécurisé les connections  
   Les solutions actuelles  
   ...  

## Développement  

  ###  ***SSH***  
  
   Secure Shell (SSH) est à la fois un programme informatique et un protocole de communication sécurisé. Le protocole de connexion impose un échange de clés de         chiffrement en début de connexion. Par la suite, tous les segments TCP sont authentifiés et chiffrés. Il devient donc impossible d'utiliser un sniffer pour voir ce que fait l'utilisateur.

Le protocole SSH a été conçu avec l'objectif de remplacer les différents protocoles non chiffrés comme rlogin, telnet, rcp et rsh.

   ###### Quels problème pour le ssh ?  


  ### ***Pare-feu***  
  
   Un pare-feu (de l'anglais firewall) est un logiciel et/ou un matériel permettant de faire respecter la politique de sécurité du réseau, celle-ci définissant quels sont les types de communications autorisés sur ce réseau informatique. Il surveille et contrôle les applications et les flux de données (paquets).
   
   ###### Quels problème pour le Pare-feu ?  

  ### ***Brute Force***  
  
  L'attaque par force brute est une méthode utilisée en cryptanalyse pour trouver un mot de passe ou une clé. Il s'agit de tester, une à une, toutes les combinaisons possibles.

Cette méthode est en général considérée comme la plus simple concevable. Elle permet de casser tout mot de passe en un temps fini indépendamment de la protection utilisée, mais le temps augmente avec la longueur du mot de passe. En théorie la complexité d'une attaque par force brute est une fonction exponentielle de la longueur du mot de passe, la rendant en principe impossible pour des mots de passe de longueur moyenne. En pratique des optimisations heuristiques peuvent donner des résultats dans des délais beaucoup plus courts.

Cette méthode est souvent combinée avec l'attaque par dictionnaire et par table arc-en-ciel pour trouver le secret plus rapidement.

  ###### Quels problèmes créé le Brute Force ?  

  ### ***Fail2Ban***  
  
  Fail2ban est une application qui analyse les logs de divers services (SSH, Apache, FTP…) en cherchant des correspondances entre des motifs définis dans ses filtres et les entrées des logs. Lorsqu'une correspondance est trouvée une ou plusieurs actions sont exécutées. Typiquement, fail2ban cherche des tentatives répétées de connexions infructueuses dans les fichiers journaux et procède à un bannissement en ajoutant une règle au pare-feu iptables ou nftables pour bannir l'adresse IP de la source.

 ###### Quels problèmes à le Fail2Ban ?  

## Démonstration  

   ###### Création d'une Machine virtuelle pour démontrer les différents problèmes de chaque partie. A chaque fois, faire cette démonstration après la réponses aux questions "Quels problèmes...?"  
   
   ##### Machine virtuelle qui propose des solutions à chaque problème potentiels.
   
   ##### Ouverture sur des potentiels solution non accessible pour le moment ou à notre niveau

## Conclusion et potentiel solution aux problèmes  

# Sources  
[Site de Test](https://www.youtube.com/watch?v=dQw4w9WgXcQ)  
[Wikipedia](https://Wikipedia.com)  
[Wiki-Ubuntu](https://doc.ubuntu-fr.org)  

