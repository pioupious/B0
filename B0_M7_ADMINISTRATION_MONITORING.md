# Administration Monitoring 


| Commande      | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| `top`         | Afficher les processus en cours en live 
| `ps`          | Affiche les proccessus principaux en cours sur le moment donné         |
| `ps -aux`          | Affiche tout les proccessus en cours en live sur le moment donné           |
| `kill -9`     | Tue un process en cours                                               |
| `pgrep "..."`      | recherche le nom donné parmis les satus                                                      |
| `systemctl status`     | Affiche des information sur le status mentionné      |
| `systemctl stop`     | Mets en pause le status      |
| `systemctl start`     | Relance le status mis en pause   |
| `systemctl restart`     | Redemare un status   |
| `systemctl enable`     | Active le status au demarage      |
| `systemctl disable`     | Desactive le service au demarage    |
| `systemctl reload`     | Actualise le status     |
| `systemctl daemon-reload` | relance tout les processus en cours  |
| `df -h`     | Affiche  l'espace disque   |
| `free`     | Affiche  l'utilisation de la RAM   |
| `du -sh /.../`     | Affiche  l'espace d'un repertoire   |
| `tail -20 -f`     | Affiche en live les 20 dernière lignes    |

----------
| Commande      | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| `journalctl`         |Affiche tous les logs système, du plus ancien au plus récent. |
| `journalctl -u <nom_du_service>`      |Filtre les logs pour un service spécifique (exemple : journalctl -u ssh).         |
| `journalctl -xeu <nom_du_service>`          | Affiche les logs détaillés pour un service en commençant par lesderniers logs (-e)           |
| `journalctl -f`     |Affiche les nouveaux logs en temps réel (mode "follow").                                   |
| `journalctl -b`         |Affiche les logs depuis le dernier démarrage du système. |
| `journalctl -g <mot-clé>`      |Recherche des logs contenant un mot-clé spécifique         |
| `journalctl --since <date>`          | Affiche les logs depuis une date/heure spécifique (exemple : --since "2023-10-01") (exemple : --since "3 hours ago")      |
| `journalctl --until <date>`     |Affiche les logs jusqu'à une date/heure spécifique.      | 
| `journalctl > logs.txt`     |Exporte les logs dans un fichier texte pour analyse ultérieure      | 

-----

| Répertoir     | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| /run/log/journal/        | Logs temporaires (effacés au redémarrage) |
| /var/log/journal/      |  Logs persistants (si le répertoire existe et est configuré)         |
| /etc/fstab       | montage des partitions        |
|  /etc/passwd        | comptes utilisateurs       |
| /etc/network/interfaces      | configuration réseau        |
| /etc/systemd/system       | Endroit ou se trouvent les services     |

-----

Quelle commande permet d'afficher tous les logs géné-
rés depuis 3 heures du service NetworkManager ?
_journalctl -xeu NetworkManager --since "3 hours ago"_

Comment vous utiliseriez journalctl pour diagnostiquer
les problèmes de l’utilisateur stagiaire ?
_journalctl -g stagiaire_

Expliquez en quelques lignes comment vous utiliseriez
systemctl et journalctl pour diagnostiquer un problème
de démarrage d'un service spécifique (par exemple,
Apache).

_Verif l'état de Apache2_ :
```systemctl status apache2```

_Si le service est arrêté _:
```systemctl start Apache2```

_Verif l'état de Apache2_ :
```systemctl status apache2```

_Si besoin, inspecter les lod du service_ :
```journalctl -xeu Apache2```

# Sauvegardes

La commande tar (pour Tape ARchive) est un outil puissant sous Linux pour créer, extraire et gérer des ar-
chives de fichiers. Elle permet de regrouper plusieurs fichiers et répertoires en une seule archive, souvent
compressée avec gzip (option -z) ou bzip2. Très utile pour les sauvegardes, elle offre des options comme -c
(créer), -x (extraire), et -v (affichage détaillé)

```
**créer archives**
 tar [options] [fichier-archive] [fichier ou répertoire à archiver]

exemple :
tar -czvf nom_archive.tar.gz /chemin/vers/répertoire_ou_fichier
tar -cvf exemple.tar fichier1.txt fichier2.txt répertoire1

**extraire archive**

tar -C répertoire_destination/ -xvf exemple.tar


``` 

# Automatisations taches CRON

Une tâche cron est une tâche exécutée automatiquement dans un système d’exploitation. Afin d’exécuter ces tâches, le système fournit régulièrement des commandes. Il peut parfaitement s’agir d’une simple tâche, mais, en règle générale, on utilise plusieurs tâches complexes, donc plusieurs cron jobs.
Le fichier système standard Crontab « crontab » est placé dans le répertoire /etc/cron.*/.



```
crontab -e
------

*     *     *     *     * Commande à exécuter
-      -      -      -     -
|     |     |     |     |
|     |     |     |     +----- Jour de la semaine (0 - 7) (Dimanche correspond à 0 et 7)
|     |     |     +------- Mois (1 - 12)
|     |     +--------- Jour (1 - 31)
|     +----------- Heure (0 - 23)
+------------- Minute (0 - 59)


exemple :
0 8,18 * * * /usr/bin/send_reminder_mail.sh

``` 


