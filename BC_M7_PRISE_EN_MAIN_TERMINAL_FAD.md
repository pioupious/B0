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

- **Le type Fichier**
```bash 
file "namefile"
```

---

- **Le type de commande **
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
  
_affiches toutes les commande utilisée y compris celles des précédents bash_

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

- **Afficher du text dans le bash**
```bash 
echo je m'appel pierre
```
ou 
```bash 
echo "je m'appel pierre"
```

---

- **Transfert de texte**
- 
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
  

  _possible avec aptitude_
  
```bash 
aptitude
```

**Mais en général !**

_Recherche de mise à jours_

```bash
sudo apt-get update
```

_Application des mises à jours_

```bash 
sudo apt-get upgrade
```

_Recherche d'application tiers_

```bash 
sudo apt-cache search gimp
```

_Instalation de application tiers précédement recherchée_

```bash 
sudo apt-cache install gimp
```

_Supprimer un paquet = garder les fichier de configuration_

```bash 
sudo apt-get remove gimp
```

_Purge un paquet = delet tout_

```bash 
sudo apt-get purge gimp
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

_La commande va renvoyé la ou les lignes du fichier choisi qui contient le mots_
  
```bash 
grep 'mots à trouver' ~/Téléchargements ...
```

---

- **Shutdown**
  
_La commande permet d'éteindre la machine doit venir avec des **indation de temps** et **nécéssite une élévation root**_
  
```bash 
shutdow now

shutdonw 12:00
```

---

- **Commandes Réseau**
  
_La commande permet d'afficher les cartes et informations réseaux_
  
```bash 
iwconfig

ifconfig
```

_Envoyer un ping a un réseau_

```bash 
ping 8.8.8.8
```
_Possible de quantifier le nb de ping_

```bash 
ping -c (nombre) 8.8.8.8
```
**ex:** ping -c 4 8.8.8.8

---

- **Affichage des processus**
  
_La commande permet d'afficher les processus en cours_
  
```bash 
ps
```
 * PID : L'identifiant du processus, qui est unique au processus. Ces informations sont utiles pour contrôler le processus par son numéro d'identification.

 * TTY : Le nom du terminal sur lequel le processus est en cours d'exécution. Ces informations sont utiles pour distinguer les différents processus qui portent le même nom.

 * TIME : Le temps processeur utilisé par le processus. Généralement, cette information n'est pas utilisée par les utilisateurs standards.

 * CMD : La commande qui a lancé le processus.
   

L'option -e affichera tous les processus 


l'option -f est également utilisée car elle fournit plus de détails dans l'affichage de la commande

---

- **Modifier le Password**
  
_La commande permet de changer la mots de passe_
  
```bash 
passwd
```

-S utilisateur    peux etre utiliser pour avoir des infos sur le Password sur l'utilisateur

_L'utilisateur root peut modif tout les mots de passes_

- **Téléchargements**
  
_La commande permet de télécharger des fichier_
  
```bash 
wget (chemin)
```

- **Transfert de fichier via ssh **
  
_Permet de transferer des fichier de fc=acon sécurisée_
  
```bash 
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```
_Je prend le fichier important.txt et je le transfert a /ubuntu sous le nom de tranfert.txt

```bash 
scp  ubuntu@192.168.1.30:/home/ubuntu/transferred.txt important.txt
```
_C'est dans le sens inverse transferred.txt est transferet sur ma pasition et renomé transfert.txt_

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

_Autre methode_

1 = x ou execute

2 = w ou Write

4 = r ou read

3 = wx

5 = rx

6 = rw

7 = xwr

```bash 
chmod [1-7][1-7][1-7] [file name ou file pass]
```
**exemple :** 
```bash 
chmod 744 ~/Téléchargements/test.txt
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

'Tes.t' ou 'Te..t' ou encore 'T....' = 	Un seul caractère par points

' ' = N'importe quel caractère spécifié

'[^test] ' = 	Pas le caractère spécifié

'te*t '= Zéro ou plus du caractère précédent

'^test' = Si premier caractère du motif, le motif doit être au début de la ligne pour correspondre, sinon cela correspond à un caractère caret ^ littéral.

'test$' =	Si dernier caractère du motif, le motif doit être à la fin de la ligne pour correspondre, sinon cela correspond à un signe dollar $ littéral.

+ =	Un ou plusieurs du motif précédent

{ } =	Spécifier correspondances minimum, maximum ou exactes du motif précédent

? =	Le motif précédent est optionnel

| = 	Alternance - un "ou" logique

( ) =	Utilisé pour créer des groupes

