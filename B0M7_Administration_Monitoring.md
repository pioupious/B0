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
| `journalctl --since <date>`          | Affiche les logs depuis une date/heure spécifique (exemple : --since "2023-10-01") (exemple : --since "3 hours ago")           |
| `journalctl --until <date>`     |Affiche les logs jusqu'à une date/heure spécifique.      | 
| `journalctl > logs.txt`     |Exporte les logs dans un fichier texte pour analyse ultérieure      | 

-----

| Réperoir     | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| `top`         | Afficher les processus en cours en live 
| `ps`          | Affiche les proccessus principaux en cours sur le moment donné         |
| `ps -aux`          | Affiche tout les proccessus en cours en live sur le moment donné           |

-----

Quelle commande permet d'afficher tous les logs géné-
rés depuis 3 heures du service NetworkManager ?
_journalctl -xeu NetworkManager --since "3 hours ago"_

Comment vous utiliseriez journalctl pour diagnostiquer
les problèmes de l’utilisateur stagiaire ?
_journalctl -g stagiaire_




