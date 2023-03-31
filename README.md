# Projet-R&C2  
  ###### Projet - Bachelor Cybersécurité et Réseaux Argenteuil - Thème Hardening: Protocole de couche 3 et 4  

## Introduction  

  ### ──────────【 Définition des Parties 】────────── ###
   * Qu'est-ce que le SSH ?  
   * Qu'est-ce que ...  
  
  ### Ouverture sur tout les problèmes liés aux couches 3 et 4 ###
   * Comment sécurisé les connections  
   * Les solutions actuelles  
   * ...  

## Développement  

  ### ──────────【 ***SSH*** 】────────── ###  
  
   Secure Shell (SSH) est à la fois un programme informatique et un protocole de communication sécurisé. Le protocole de connexion impose un échange de clés de         chiffrement en début de connexion. Par la suite, tous les segments TCP sont authentifiés et chiffrés. Il devient donc impossible d'utiliser un sniffer pour voir ce que fait l'utilisateur.

Le protocole SSH a été conçu avec l'objectif de remplacer les différents protocoles non chiffrés comme rlogin, telnet, rcp et rsh.

   ###### Quels problème pour le ssh ?  
   
   L'utilisation du protocole SSH peut présenter plusieurs problèmes, notamment en matière de sécurité, de performances et de compatibilité.

L'un des principaux problèmes de sécurité liés à l'utilisation de SSH est la possibilité d'attaques par force brute. Les attaquants peuvent essayer de deviner les informations d'identification en essayant toutes les combinaisons possibles de noms d'utilisateur et de mots de passe. Bien que les implémentations SSH modernes soient généralement protégées contre de telles attaques, elles peuvent toujours constituer une menace pour les systèmes mal configurés ou qui utilisent des mots de passe faibles.

Un autre problème de sécurité est la vulnérabilité aux attaques de l'homme du milieu (MITM). Les attaquants peuvent intercepter le trafic SSH et essayer de modifier les données en transit. Les implémentations modernes de SSH utilisent des clés publiques pour s'assurer que les données sont chiffrées de bout en bout et ne peuvent pas être modifiées en transit. Cependant, si les clés publiques sont compromises, cette protection peut être mise en échec.

Un autre problème de sécurité lié à l'utilisation de SSH est la gestion des clés. Les clés SSH sont utilisées pour établir des connexions sécurisées entre des machines, mais leur gestion peut être complexe et potentiellement vulnérable. Si les clés privées sont compromises, un attaquant peut accéder aux systèmes distants sans même avoir besoin de connaître le mot de passe.

En termes de performances, l'utilisation de SSH peut être plus lente que les protocoles non chiffrés tels que Telnet. Cela est dû au temps supplémentaire nécessaire pour chiffrer et déchiffrer les données. Bien que la différence de vitesse soit généralement minime, elle peut devenir importante dans les environnements à forte charge ou pour les tâches intensives en termes de bande passante.

Un autre problème de performance lié à l'utilisation de SSH est la capacité des serveurs à gérer de nombreuses connexions simultanées. Les serveurs SSH peuvent être surchargés si trop de connexions sont établies en même temps, ce qui peut entraîner une latence accrue ou même des échecs de connexion. Il est important de configurer les serveurs SSH de manière appropriée pour éviter ces problèmes.

Enfin, la compatibilité peut être un problème avec SSH. Bien que le protocole soit largement utilisé, certains systèmes peuvent ne pas le prendre en charge ou ne pas être en mesure d'établir une connexion. Il est important de vérifier la compatibilité des systèmes avant de tenter de se connecter via SSH.

En résumé, l'utilisation de SSH présente plusieurs problèmes potentiels en termes de sécurité, de performances et de compatibilité. Ces problèmes peuvent être évités ou minimisés en prenant des mesures appropriées, telles que l'utilisation de mots de passe forts, la gestion des clés, la configuration des serveurs, la vérification de la compatibilité et la surveillance des activités suspectes.


  ### ──────────【 ***Pare-feu*** 】────────── ###  
  
   Un pare-feu (de l'anglais firewall) est un logiciel et/ou un matériel permettant de faire respecter la politique de sécurité du réseau, celle-ci définissant quels sont les types de communications autorisés sur ce réseau informatique. Il surveille et contrôle les applications et les flux de données.
   
   ###### Quels problème pour le Pare-feu ?  
   
   Les pare-feux ont pour rôle de protéger les réseaux informatiques des menaces extérieures en surveillant et contrôlant les flux de données. Cependant, ils peuvent être à l'origine de plusieurs problèmes :

Faux positifs : Les pare-feux utilisent souvent des règles pour filtrer le trafic. Ces règles peuvent être trop restrictives et bloquer des connexions légitimes, créant ainsi des faux positifs. Par exemple, un pare-feu peut bloquer une connexion VPN légitime en raison d'une règle mal configurée.

Surcharge : Les pare-feux sont souvent utilisés pour contrôler et limiter le trafic réseau. Cependant, cette limitation peut parfois causer une surcharge du pare-feu. Par exemple, une attaque par déni de service (DoS) peut submerger un pare-feu en envoyant une quantité excessive de trafic, le rendant incapable de traiter les demandes légitimes.

Coût : Les pare-feux matériels peuvent être coûteux, en particulier pour les petites entreprises qui ont un budget limité pour la sécurité informatique. De plus, les pare-feux nécessitent souvent une configuration et une maintenance régulières, ce qui peut entraîner des coûts supplémentaires.

Complexité : Les pare-feux peuvent être difficiles à configurer et à maintenir, surtout pour les utilisateurs non expérimentés. Une mauvaise configuration peut entraîner une diminution de l'efficacité du pare-feu ou même créer des vulnérabilités.

Contournement : Les pare-feux peuvent être contournés par des attaquants expérimentés. Par exemple, un attaquant peut utiliser un tunnel SSH pour contourner un pare-feu qui bloque les connexions SSH.

Fuites de données : Les pare-feux ne sont pas toujours en mesure de protéger les données sensibles. Par exemple, les pare-feux ne peuvent pas empêcher les utilisateurs autorisés d'exfiltrer des données sensibles via des canaux non autorisés, tels que les supports de stockage USB.

Mise à jour : Les pare-feux doivent être mis à jour régulièrement pour rester efficaces contre les nouvelles menaces. Cependant, la mise à jour d'un pare-feu peut être complexe et nécessiter une interruption des services. De plus, la mise à jour peut causer des conflits avec les autres logiciels ou matériels du réseau.

En somme, les pare-feux sont des outils de sécurité informatique importants, mais ils peuvent également causer des problèmes s'ils ne sont pas configurés et maintenus correctement. Les utilisateurs doivent être conscients des problèmes potentiels liés aux pare-feux et prendre des mesures pour les atténuer.

  ### ──────────【 ***Brute Force*** 】────────── ###  
  
  L'attaque par force brute est une méthode utilisée en cryptanalyse pour trouver un mot de passe ou une clé. Il s'agit de tester, une à une, toutes les combinaisons possibles.

Cette méthode est en général considérée comme la plus simple concevable. Elle permet de casser tout mot de passe en un temps fini indépendamment de la protection utilisée, mais le temps augmente avec la longueur du mot de passe. En théorie la complexité d'une attaque par force brute est une fonction exponentielle de la longueur du mot de passe, la rendant en principe impossible pour des mots de passe de longueur moyenne. En pratique des optimisations heuristiques peuvent donner des résultats dans des délais beaucoup plus courts.

Cette méthode est souvent combinée avec l'attaque par dictionnaire et par table arc-en-ciel pour trouver le secret plus rapidement.

  ###### Quels problèmes créé le Brute Force ?  

  ### ──────────【 ***Fail2Ban*** 】────────── ###  
  
  Fail2ban est une application qui analyse les logs de divers services (SSH, Apache, FTP…) en cherchant des correspondances entre des motifs définis dans ses filtres et les entrées des logs. Lorsqu'une correspondance est trouvée une ou plusieurs actions sont exécutées. Typiquement, fail2ban cherche des tentatives répétées de connexions infructueuses dans les fichiers journaux et procède à un bannissement en ajoutant une règle au pare-feu iptables ou nftables pour bannir l'adresse IP de la source.

 ###### Quels problèmes à le Fail2Ban ?  

## Démonstration  

   ###### Création d'une Machine virtuelle pour démontrer les différents problèmes de chaque partie. A chaque fois, faire cette démonstration après la réponses aux questions "Quels problèmes...?"  
   
   * Machine virtuelle qui propose des solutions à chaque problème potentiels.  
   ###### Machine Kali Linux
   
   * Ouverture sur des potentiels solution non accessible pour le moment ou à notre niveau  

## Conclusion et potentiel solution aux problèmes  

# Sources  
[Site de Test](https://www.youtube.com/watch?v=dQw4w9WgXcQ)  
[Wikipedia](https://Wikipedia.com)  
[Wiki-Ubuntu](https://doc.ubuntu-fr.org)  

