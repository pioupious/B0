# ALL COMMANDES 

## GESTION UTILASATEUR


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


- **Modif User Droit**

  ```bash
  usermod -a -g 1001 stagiaire -G sudo nomuser
  ```

-a add des groupe sinon le  

-g quel groupe on veux le mettre, 1001 pas obligé mais id du groupe

-G quel groupe secondaire on le mets


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

## DROIT SUPERVISION PAQUET

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

# FONTIONNEMENT


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
