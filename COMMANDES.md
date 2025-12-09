# ALL COMMANDES 

## GESTION UTILISATEUR


- **Créer un compte user**

_créer un user pose les questions plus simple_
  
```bash 
adduser jesuispierre
```

---

- **Add un compte user**

_Add un user pause pas de question mais plus compliquer_
  
```bash 
useradd -d /home/pioupiouLove -m -s /bin/bash -g stagiaire -G sudo -u 1002 pioupiou2
```
-d = créer un directory

-m prendre en compte l'arbo crée 

-s donne accès shell dans bin/bash

-g groupe stagiaire

-G groupe secondaire sudo 

-u user numero 1002 et nom piopiou2



- **Delet un user**
  
_add un user pause pas de question mais plus compliquer_
  
```bash 
userdel nom
```

**important:** -r pour delet les directory 

---
- **Se connecter a un user**
  
_permet d'agir sur le répertoire d'un user en tant que ce user_
  
```bash 
su - usernom
```

_pour un ordi a distance avec le SSH_

```bash 
ssh nomuser@MACHINE_IP 
```

---


- **Changer Password**
  
_modifier le mots de passe_
  
```bash 
passwd nom
```
necessite d'etre sur le user ou etre root

-e invalide le mots et oblige l'utilisateur a utiliser un nouveau mdp

-l supprime le mots de pass = utilisateur ne paut plus se co 

-S information sur le mot de passe avec -a all

---


- **Céer un groupe**
  
_créer un groupe_
  
```bash 
groupadd nom
```
-trouver les groupe sur /ect/group

```bash 
cat /ect/group
```

- **Delet groupe**
  
```bash 
delgroup nom
```

- Penser a remove le groupe Users lors de la création si adduser


---


- **Inform de la modification d'un fichier**
  
```bash 
pwck cheminom
```

---
## BUREAUTIQUE ET FICHIER


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

## SUPERVISION PAQUET


- **Information compte**
  
_permet d'avoir des info sur un compte_
  
```bash 
id nom
```

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
  
_La commande permet d'afficher les processus en cours dans le user au moment de la commande_
  
```bash 
ps
```
 * PID : L'identifiant du processus, qui est unique au processus. Ces informations sont utiles pour contrôler le processus par son numéro d'identification.

 * TTY : Le nom du terminal sur lequel le processus est en cours d'exécution. Ces informations sont utiles pour distinguer les différents processus qui portent le même nom.

 * TIME : Le temps processeur utilisé par le processus. Généralement, cette information n'est pas utilisée par les utilisateurs standards.

 * CMD : La commande qui a lancé le processus.
   

L'option -e affichera tous les processus 


l'option -f est également utilisée car elle fournit plus de détails dans l'affichage de la commande

_Pour afficher tout les processus sur tout les users_


```bash 
ps aux
```

---

- **Affichages des porcessus en live**
  
_La commande permet de voir les proceesus en live _
  
```bash 
top
```

---- 

- **Arreter un processus**
  
_A utiliser avec top localiser id du processus puis_
  
``` 
kill id
```

_Proprement (fait du clean avant de fermer la tache)_


``` 
SIGTERM
```

_Supend un process_
``` 
SIGSTOP
```
---- 

- **Téléchargements**
  
_La commande permet de télécharger des fichier_
  
```bash 
wget (chemin)
```

---- 

- **Transfert de fichier via ssh**
  
_Permet de transferer des fichier de fc=acon sécurisée_
  
```bash 
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```
_Je prend le fichier important.txt et je le transfert a /ubuntu sous le nom de tranferred.txt

```bash 
scp  ubuntu@192.168.1.30:/home/ubuntu/transferred.txt important.txt
```
_C'est dans le sens inverse transferred.txt est transferet sur ma pasition et renomé transfert.txt_



# FONTIONNEMENT


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


## Les Droits

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
**Changer valeur par Default des droits fichier**
```
umask 133
```
_touch créera un fichier 744 en droit_

Utilisateur et other on leurs droits **changer** en **write** et **read** sur le fichier **test.txt** situé dans **Télécharments**

**Priopriétaire et Groupe**
_Changer le propriétaire du fichier_


**nécéssite une elevation de droit**

_chown = change own = changer le proprio_

```bash 
sudo chown Root ~/Téléchargements/test.txt
```

---

- **Modif User Droit**

  ```bash
  usermod -a -g 1001 stagiaire -G sudo nomuser
  ```

-a add des groupe sinon le  

-g quel groupe on veux le mettre, 1001 pas obligé mais id du groupe

-G quel groupe secondaire on le mets


# Serveur  Web

- **merttre en place un serveur web**

_permet de créer un serveur web_
  
```bash 
python3 -m http.server
```
_Puis ctrl + C pour end le serveur_

---
