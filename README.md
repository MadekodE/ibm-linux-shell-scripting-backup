# **Linux Commands and Shell Scripting : Projet final / IBM Data Engineering Professional-Certificate**



## **Scénario**



Imaginez que vous êtes un développeur Linux principal au sein de la société de haute technologie ABC International Inc. ABC souffre actuellement d'un énorme goulot d'étranglement : chaque jour, les stagiaires doivent laborieusement accéder aux fichiers de mots de passe cryptés sur les serveurs centraux et sauvegarder tous les fichiers qui ont été mis à jour au cours des dernières 24 heures. Ce processus introduit une erreur humaine, diminue la sécurité et demande une quantité de travail déraisonnable.



En tant que l'un des développeurs Linux les plus fiables d'ABC Inc., vous avez été chargé de créer un script appelé backup.sh qui s'exécute tous les jours et sauvegarde automatiquement tous les fichiers de mots de passe cryptés qui ont été mis à jour au cours des dernières 24 heures.



## **Objectifs d'apprentissage**



En réalisant ce projet final, vous allez



* Démontrer vos compétences avancées en matière de scripts shell dans un scénario réel



* Appliquer les connaissances acquises à la révision et à la notation de travaux techniques.



Après la création du script backup.sh, les commandes suivantes sont exécutées dans le terminal:



**# Rendre le script exécutable**



chmod u+x backup.sh



**# Vérifier que le fichier est exécutable**



ls -l backup.sh



**# Télécharger ce fichier ZIP**



wget https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-LX0117EN-SkillsNetwork/labs/Final%20Project/important-documents.zip



**# Décompresser l’archive**



unzip -DDo important-documents.zip



**# Mettre à jour la date de dernière modification des fichiers pour la définir à la date et à l’heure actuelles**



touch important-documents/\*



**# Tester le script afin de créer un fichier nommé backup-\[CURRENT\_TIMESTAMP].tar.gz dans le répertoire courant**



./backup.sh important-documents .



**# Copier le script backup.sh dans le répertoire /usr/local/bin/**



sudo cp backup.sh /usr/local/bin/



\# **Ouvrir l’éditeur de la table des tâches planifiées** cron



crontab -e



\# **Planifier l’exécution du script de sauvegarde** /usr/local/bin/backup.sh **toutes les 24 heures, afin de sauvegarder le dossier important-documents dans le répertoire personnel** (\~)



0 0 \* \* \* /usr/local/bin/backup.sh /home/project/important-documents /home/project



**# Afficher toutes les tâches planifiées avec cron**



crontab -l

