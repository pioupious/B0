# Rappel des commandes Linux
 Le terminal Linux est une interface en ligne de commande il permet d'exécuter des commandes pour naviguer dans les
 fichiers, gérer les processus et configurer le système. Il utilise des in
terpréteurs de commandes comme Bash sous Debian. Les utilisateurs
 peuvent automatiser des tâches grâce aux scripts Shell. Son utilisation est essentielle pour l'administration
 et le développement sur Linux
 
## Differents répertoires

- / (racine) : Contient tous les fichiers et répertoires du système.

 - */bin & /sbin* : Programmes et commandes essentielles pour tous les utilisateurs (bin) et pour l'ad
ministration (sbin).
 - */etc* : Fichiers de configuration du système et des services.
- */home* : Dossiers personnels des utilisateurs (ex. /home/stagiaire).
- */var* : Données variables comme logs (/var/log) et files d’attente (/var/spool).
- */usr* : Logiciels et bibliothèques utilisateur (/usr/bin, /usr/lib).
- */opt* : Applications tierces installées manuellement.
- */tmp* : Fichiers temporaires supprimés au redémarrage.
- */dev, /proc, /sys* : Systèmes de fichiers spéciaux pour les périphériques et processus.
- */boot* : Contient les fichiers nécessaires au démarrage, comme le noyau Linux (vmlinuz), le chargeur
 de démarrage (GRUB).
- */media* : Points de montage pour les périphériques amovibles (clés USB, disques durs externes,
 CD/DVD).
- */mnt* : Point de montage temporaire pour des systèmes de fichiers externes.
- */root* : Dossier personnel de l'utilisateur root (administrateur).
- */run* : Stocke les informations volatiles du système (PID, sockets, fichiers de verrouillage) après le
 démarrage.
- */srv* : Contient les données des services hébergés par le système (serveurs web, FTP, etc.)

## Commande

lien pour voir commande : https://phoenixnap.com/kb/linux-commands 

- *Droit root mais pas dieu de l'ordi*
```bash 
su
```

- *Dieu sur l'ordi*
```bash 
su -
```

- *Indiqué ce qu'il y a dans un directory*
```bash 
ls
```
Option possible : -l (liste), -/ l'interieur de l'arboressance, -a (affiche fichier caché)

- *Change directory = bouger dans l'arboressance linux*
```bash 
cd
```
Option possible :  cd .. (remonte de 1), cd ~ et cd (retourne dans home) 

exemple: cd ../Téléchargement
cd ~

- *Affiche le chemin du directory dans lequel on est où je suis?*
```bash 
pwd 
```

- *Permet d'avoir de l'aide*
```bash
--help 
```

- *Le type de commande ou Fichier*
```bash 
type 
```

- *Equivalent de help*
```bash 
man 
```


- *creer un folder*
```bash 
mkdir 
```


- *Remove file*
```bash 
rm
```
si folder
```bash 
rm -R
```

- *copy and paste*
```bash 
cp /.. /..
```
pour contenu
```bash 
cp /..*  /..
```
Option: -R pour tout l'arbo choisi

- *Créer folder*
```bash 
touch /Téléchargement 
```

- *historique de toutes les commande*
```bash 
history
```

- *trouver un folder*
```bash 
find -name ...
```
