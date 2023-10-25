# Projet-R&C
  ###### Projet - Bachelor Cybersécurité et Réseaux Argenteuil - Thème Durcissement d'accès

# Fail2ban

Fail2ban est un outil de sécurité essentiel pour protéger un serveur contre les tentatives de connexion malveillantes. Il fonctionne en surveillant les journaux système pour détecter les comportements suspects, tels que des tentatives de connexion infructueuses répétées, et en bloquant les adresses IP responsables. Voici un guide sur l'installation, la configuration et la maintenance de Fail2ban.

## Installation de Fail2ban

**Étape 1 : Mise à jour du système**
Assurez-vous que votre système est à jour.
```shell
sudo apt update
```
**Étape 2 : Installation de Fail2ban**
Installez Fail2ban.
```shell
sudo apt install fail2ban
```

## Configuration de Fail2ban

**Étape 3 : Copie du fichier de configuration**
Pour personnaliser la configuration, copiez le fichier de configuration par défaut.
```shell
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```
**Étape 4 : Modification de la configuration**
Éditez le fichier `jail.local` pour personnaliser les règles de bannissement.

**Étape 5 : Configuration des actions**
Configurez les actions à entreprendre lorsqu'une adresse IP est bannie.

**Étape 6 : Activation au démarrage**
Activez Fail2ban pour qu'il démarre automatiquement lors du démarrage du système.
```shell
sudo systemctl enable fail2ban
```
## Démarrage et Maintenance

**Étape 7 : Démarrage de Fail2ban**
Démarrez Fail2ban.
```shell
sudo systemctl start fail2ban
```

**Étape 8 : Vérification de l'état**
Vérifiez l'état de Fail2ban pour vous assurer qu'il fonctionne correctement.
```shell
sudo systemctl status fail2ban
```


**Étape 9 : Surveillance des journaux**
Surveillez régulièrement les journaux de Fail2ban pour détecter d'éventuelles activités suspectes.

**Étape 10 : Mises à jour**
Assurez-vous de maintenir votre installation Fail2ban à jour en utilisant les mises à jour système régulières.

Fail2ban est un outil précieux pour renforcer la sécurité de votre serveur en protégeant contre les attaques de force brute. En suivant ce guide, vous pouvez installer, configurer et maintenir Fail2ban pour assurer une protection efficace de votre serveur.

"Installation, Configuration et Maintenance de Knockd

# Knockd
Sous Linux, vous pouvez installer Knockd en utilisant le gestionnaire de paquets de votre distribution.
```shell
sudo apt-get install knockd
```

## Configuration

Une fois installé, la configuration de Knockd est essentielle. Suivez ces étapes pour configurer Knockd :

### Fichier de Configuration
Le fichier de configuration de Knockd est généralement situé à `/etc/knockd.conf`. Utilisez un éditeur de texte pour l'ouvrir en tant qu'administrateur.

### Sections de Configuration
Le fichier de configuration est divisé en sections, chacune définissant un ensemble de règles pour déclencher des actions. Personnalisez ces sections en fonction de vos besoins de sécurité et des services que vous souhaitez protéger.
```shell
[options]
logfile = /var/log/knockd.log

[openSSH]
sequence    = 7000,8000,9000
seq_timeout = 5
command     = /sbin/iptables -A INPUT -s %IP% -p tcp --dport 22 -j ACCEPT
```
## Démarrage de Knockd

Après avoir configuré Knockd, démarrez-le pour activer son fonctionnement.
```shell
sudo service knockd start
```


## Maintenance

La maintenance de Knockd consiste en la surveillance, la mise à jour et le suivi de son fonctionnement.

### Surveillance du Journal
Surveillez régulièrement le journal pour les tentatives de frappes et les déclenchements d'actions. Cela vous permettra de repérer toute activité suspecte.

### Mise à jour de la Configuration
Si vos besoins en matière de sécurité évoluent, mettez à jour la configuration de Knockd en ajoutant ou modifiant des séquences et des actions. Assurez-vous de comprendre l'impact de ces changements sur votre pare-feu.

### Pare-feu
Gardez à l'esprit que Knockd repose sur des règles de pare-feu. Veillez à maintenir ces règles de manière appropriée et sécurisée.

### Tests de Sécurité
Réalisez régulièrement des tests de sécurité pour vérifier l'efficacité de Knockd et de votre pare-feu.

### Sauvegardes
Sauvegardez régulièrement votre configuration Knockd et les règles du pare-feu. Cela permet de récupérer rapidement en cas de problèmes.

En conclusion, l'installation, la configuration et la maintenance de Knockd peuvent considérablement renforcer la sécurité de votre serveur. Cependant, assurez-vous de comprendre en profondeur son fonctionnement et ses implications sur votre réseau, et surveillez activement son activité pour réagir aux menaces potentielles."