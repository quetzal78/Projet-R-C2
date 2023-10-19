# Projet-R&C
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
  
  Les attaques par force brute sont une méthode utilisée en cryptanalyse pour trouver un mot de passe ou une clé en testant, une à une, toutes les combinaisons possibles. Bien que cette méthode soit considérée comme la plus simple concevable pour casser des mots de passe, elle reste très coûteuse en termes de temps. En effet, la complexité d'une attaque par force brute est une fonction exponentielle de la longueur du mot de passe, la rendant en principe impossible pour des mots de passe de longueur moyenne. Cependant, en pratique, des optimisations heuristiques peuvent donner des résultats dans des délais beaucoup plus courts.

Les attaques par force brute peuvent poser plusieurs problèmes de sécurité. Tout d'abord, elles sont très gourmandes en ressources et en temps, ce qui peut perturber ou bloquer le système cible. En effet, le nombre de tentatives nécessaires pour casser un mot de passe augmente très rapidement avec sa longueur. Ainsi, une attaque par force brute peut rapidement saturer la bande passante du réseau ou les ressources du serveur, rendant le système cible indisponible.

De plus, les attaques par force brute peuvent causer des problèmes de confidentialité et d'intégrité des données. En effet, si un attaquant parvient à casser un mot de passe, il peut avoir accès à des données confidentielles ou les modifier, ce qui peut avoir des conséquences graves sur la sécurité de l'entreprise ou de l'utilisateur. De même, une attaque par force brute réussie peut permettre à un attaquant de prendre le contrôle d'un compte ou d'un système, ou même de pénétrer dans un réseau entier.

Une autre problématique liée aux attaques par force brute est la difficulté de les détecter. En effet, les attaques par force brute peuvent être menées de manière très discrète, avec un faible taux de tentatives par seconde, ce qui les rend difficiles à détecter avec des outils de surveillance classiques. De plus, les attaquants peuvent masquer leur adresse IP ou utiliser des réseaux de bots pour mener des attaques par force brute, ce qui rend leur traçage plus difficile.

Pour se prémunir contre les attaques par force brute, il est recommandé de prendre plusieurs mesures de sécurité. Tout d'abord, il est important de choisir des mots de passe solides et de les changer régulièrement. Les mots de passe doivent être suffisamment longs et complexes pour rendre une attaque par force brute impossible ou très coûteuse. Il est également recommandé d'utiliser des techniques de protection supplémentaires, telles que l'authentification à deux facteurs, pour renforcer la sécurité des comptes.

Ensuite, il est conseillé de limiter le nombre de tentatives de connexion autorisées avant de verrouiller un compte. Cette mesure permet de limiter les risques d'attaques par force brute, en empêchant les attaquants de lancer un grand nombre de tentatives en peu de temps. Il est également recommandé de surveiller les journaux d'activité pour détecter les tentatives d'attaques par force brute et de mettre en place des mécanismes de blocage automatique des adresses IP suspectes.

Enfin, l'utilisation d'algorithmes de hachage de mot de passe forts peut également aider à prévenir les attaques par force brute. Les algorithmes de hachage de mot de passe tels que SHA-256 et bcrypt sont beaucoup plus résistants aux attaques par force brute que les algorithmes plus anciens tels que MD5 et SHA-1. En utilisant des algorithmes de hachage de mot de passe forts, les administrateurs système peuvent réduire considérablement la probabilité qu'un attaquant réussisse à casser un mot de passe en utilisant une attaque par force brute.

En conclusion, les attaques par force brute peuvent être extrêmement dangereuses pour la sécurité des systèmes informatiques. Les attaquants peuvent utiliser des techniques de force brute pour casser des mots de passe, prendre le contrôle de systèmes et accéder à des informations sensibles. Pour lutter contre les attaques de force brute, les administrateurs système peuvent mettre en place des politiques de mot de passe solides, limiter le nombre de tentatives de connexion infructueuses, utiliser des outils tels que Fail2Ban et utiliser des algorithmes de hachage de mot de passe forts. En prenant ces mesures, les administrateurs système peuvent aider à protéger les systèmes contre les attaques de sécurité et à assurer la sécurité des données et des informations sensibles.

  ### ──────────【 ***Fail2Ban*** 】────────── ###  
  
  Fail2ban est une application qui analyse les logs de divers services (SSH, Apache, FTP…) en cherchant des correspondances entre des motifs définis dans ses filtres et les entrées des logs. Lorsqu'une correspondance est trouvée une ou plusieurs actions sont exécutées. Typiquement, fail2ban cherche des tentatives répétées de connexions infructueuses dans les fichiers journaux et procède à un bannissement en ajoutant une règle au pare-feu iptables ou nftables pour bannir l'adresse IP de la source.

 ###### Quels problèmes à le Fail2Ban ? 
 
 Fail2ban est un logiciel open source de prévention d'intrusion qui s'intègre généralement avec les pare-feux, pour bloquer les adresses IP ayant tenté de se connecter à un serveur avec des informations d'identification incorrectes à plusieurs reprises. Bien que cet outil ait de nombreux avantages en termes de sécurité, il peut également poser certains problèmes.

Tout d'abord, Fail2ban peut entraîner de faux positifs. En effet, le système peut bloquer des adresses IP qui ne sont pas des attaquants, mais des utilisateurs légitimes ayant simplement oublié leur mot de passe ou qui se sont trompés en entrant leurs informations d'identification. Si cela se produit trop souvent, cela peut entraîner des problèmes de convivialité et de satisfaction des utilisateurs, car ces derniers se verront refuser l'accès au serveur de manière incorrecte.

De plus, Fail2ban peut être contourné par des attaquants qui utilisent des adresses IP différentes à chaque tentative de connexion. Dans ce cas, le système de prévention d'intrusion ne sera pas en mesure de bloquer efficacement l'attaquant, car il ne pourra pas identifier une adresse IP particulière à bloquer.

Fail2ban peut également être contourné si les attaquants utilisent des techniques d'attaques plus avancées telles que les attaques par déni de service distribué (DDoS). Dans une telle attaque, les attaquants utilisent un grand nombre de machines compromises pour envoyer simultanément des demandes de connexion, ce qui peut surcharger le serveur et empêcher Fail2ban de détecter et de bloquer l'attaque.

En outre, Fail2ban peut également causer des problèmes de performance du serveur, en particulier si le serveur doit traiter un grand nombre de tentatives de connexion infructueuses. Cela peut surcharger le serveur et affecter les performances du système, ce qui peut entraîner des temps d'arrêt et des temps de réponse plus longs pour les utilisateurs légitimes.

Enfin, Fail2ban peut être contourné si les attaquants utilisent des techniques d'attaques plus avancées telles que les attaques par injection de code ou par exploitation de vulnérabilités du système d'exploitation ou des applications du serveur. Dans de tels cas, les attaquants peuvent contourner les mesures de sécurité mises en place, y compris Fail2ban, pour accéder au serveur et compromettre les données.

En conclusion, bien que Fail2ban soit un outil utile pour prévenir les attaques par force brute et les tentatives de connexion non autorisées, il peut également poser des problèmes s'il n'est pas correctement configuré ou utilisé de manière inappropriée. Les administrateurs système doivent être conscients des limites de Fail2ban et prendre des mesures supplémentaires pour renforcer la sécurité de leurs serveurs.


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

# Liens Utile

[Slide de présentation](https://pitch.com/public/d40e6c47-c242-4a86-9f3d-d0730c7fe1e6)
