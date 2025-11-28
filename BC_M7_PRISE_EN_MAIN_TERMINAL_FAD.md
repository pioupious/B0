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

- **Droit root mais pas dieu de l'ordi**
```bash 
su
```

---

- **Dieu sur l'ordi**
```bash 
su -
```

---

- **Indiqué ce qu'il y a dans un directory**
```bash 
ls -[option] [nom fichier]
```
*Option possible* : -l ( longue liste), -/ l'interieur de l'arboressance, -a (affiche fichier caché), -r (retournerla liste), -t (tri celon la date = time) -s (tri celon taille = size)

---

- **Change directory = bouger dans l'arboressance linux**
```bash 
cd
```
*Option possible* :  cd .. (remonte de 1), cd ~ et cd (retourne dans home) 

Exemple: cd ../Téléchargement
cd ~

---

- **Affiche le chemin du directory dans lequel on est où je suis?**
```bash 
pwd 
```

---

- **Permet d'avoir de l'aide**
```bash
--help 
```

---

- **Le type de commande ou Fichier**
```bash 
type 
```

---

- **Equivalent de help**
```bash 
man 
```
---

- **Creer un folder**
```bash 
mkdir 
```
---

- **Creer file**
```bash 
touch .../name(.txt)
```

---

- **Remove file**
```bash 
rm
```
si folder
```bash 
rm -R
```

---

- **Copy and paste**
```bash 
cp /.. /..
```
pour contenu
```bash 
cp /..*  /..
```
*Option possible* : -R pour tout l'arbo choisi

---

- **Créer folder**
```bash 
touch /Téléchargement 
```

---

- **Historique de toutes les commande**
```bash 
history
```

---

- **Trouver un folder**
```bash 
find -name ...
```

---

- **Afficher le contenu d'un file**
```bash 
cat 
```

---

- **Modif un file**
```bash 
nano
```

---

- **afficher du text dans le bash**
```bash 
echo je m'appel pierre
```
ou 
```bash 
echo "je m'appel pierre"
```

---

- **transferer du texte**
Pour transfert qui écrase
```bash 
>
```
Pour transfert qui ajoute 
```bash 
>>
```

---

- **Difference | et &&**
  
 **&&** permet de lancer un commande puis l'autre sans interconnection
**|** permet de lancer les commande a la suite et chacune prend en compte la précedante 

---

- **Gestion des paquets**
```bash 
aptitude
```

---

#**Gestion des droits utilisateur**

## Les Droits

_Plusieurs façons de faire sont possibes_

```bash 
chmod [u(user)g(groupe)o(other)a(all)][+(add)-(remove)=(assign)][w(wright)r(read)x(excute)]  [file name ou file pass]
```
**exemple :** 
```bash 
chmod uo=wx ~/Téléchargements/test.txt
```

Utilisateur et other on leurs droits **changer** en **write** et **read** sur le fichier **test.txt** situé dans **Télécharments**

## Priopriétaire et Groupe

_changer le propriétaire du fichier _

**nécéssite une elevation de droit**

_chown = change own = changer le proprio_

```bash 
sudo chown Root ~/Téléchargements/test.txt
```




# Type de Fichiers

* d ==> répertoire = Un fichier utilisé pour stocker d'autres fichiers.
* "-" ==> fichier = Inclut des fichiers lisibles, des fichiers images, des fichiers binaires et des fichiers compressés.
* l ==> lein symbolique = Pointe vers un autre fichier
* s ==> prise (socket) = Permet la communication entre les processus
* p ==> tuyau (pipe) = Permet la communication entre les processus
* b ==> fichier bloc (block file) = Utilisé pour communiquer avec le matériel
* c ==> fichier de caractères (character file) = Utilisé pour communiquer avec le matériel
