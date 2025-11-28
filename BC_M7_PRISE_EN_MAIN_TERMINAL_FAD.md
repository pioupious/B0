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

_Pour les files ou folder vide_

```bash 
rm
```
_Si folder est plein -R(récursive)_

```bash 
rm -R
```

---

- **Copy and paste**
```bash 
cp /.. /..
```

Pour prendre en compte le contenu d'un folder

```bash 
cp /..*  /..
```
*Option possible* : -R pour tout l'arbo choisi

**Alternative à mv**

```bash 
dd if=/dev/sda of=/dev/sdb
```
_if = input file | of = output file_

 * Elle peut être utilisée pour cloner ou supprimer (effacer) des disques ou des partitions entières.

 * Elle peut être utilisée pour copier des données brutes sur des périphériques amovibles, tels que des clés USB et des CD-ROMs.

 * Elle peut sauvegarder et restaurer le MBR (Master Boot Record).

 * Elle peut être utilisée pour créer un fichier d'une taille spécifique, rempli de zéros binaires, qui peut ensuite être utilisé comme un fichier swap (mémoire virtuelle).   ```bash 
             dd if=/dev/sda of=/dev/sdb bs=1M count=50
                 ```
   

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
  
_Pour afficher tout le file_

```bash 
cat ./Téléchagement/test.tx
```

_Pour afficher que les premières lignes_

```bash 
head ./Téléchagement/test.tx -n (nombre de ligne) files.txt
```

_Pour afficher que les dernières lignes_


```bash 
tail ./Téléchagement/test.tx -n (nombre de ligne) files.txt
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

- **Transfert de texte**
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

- **Déplacer des FICHIERS**

_Plusieurs fichiers peuvent etre deplacé en même temps_

```bash 
mv test.txt test01.txt test02.txt  ~/Téléchargements 
```

**ou**

```bash 
mv ~/Téléchargment/test.txt ~/Documents/test01.txt ~/Public/test02.txt  ~/Téléchargements 
```

---

- **Filtrer du texte**

_La commande va renvoyé la ou les lignes du fichier choisi qui contient le mots
  
```bash 
grep (mots à trouver) ~/Téléchargements ...
```

---




# **Gestion des droits utilisateur**

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

_Changer le propriétaire du fichier_


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

# Expressions régulières

. = 	Un seul caractère

[ ] = N'importe quel caractère spécifié

[^ ] = 	Pas le caractère spécifié

' * '= Zéro ou plus du caractère précédent

^ = Si premier caractère du motif, le motif doit être au début de la ligne pour correspondre, sinon cela correspond à un caractère caret ^ littéral.

$ =	Si dernier caractère du motif, le motif doit être à la fin de la ligne pour correspondre, sinon cela correspond à un signe dollar $ littéral.

+ =	Un ou plusieurs du motif précédent

{ } =	Spécifier correspondances minimum, maximum ou exactes du motif précédent

? =	Le motif précédent est optionnel

| = 	Alternance - un "ou" logique

( ) =	Utilisé pour créer des groupes

