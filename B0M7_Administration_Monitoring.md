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
