# GESTION_DES_UTILISATEUR_ET_DES_PROCESSUS

Dans un monde où les attaques informatiques se multiplient, **la gestion des accès et des privilèges** est essentielle
pour sécuriser un système d’informations **(SI)** . Un administrateur malveillant ou une erreur humaine peut
compromettre **l’intégrité du système** en un instant. L’objectif de cette activité est donc d’acquérir les bases pour
créer, gérer et sécuriser les **comptes** servant à **l’identification** (login) et à **l’authentification** (password) des usagers,
comprendre la gestion des permissions et analyser les **journaux** d’authentification en respectant **le principe du
moindre privilège**.

Une mauvaise gestion des **comptes utilisateurs**su  peut permettre des **élévations de privilèges ou des accès**
non autorisés.

Un utilisateur :
 - est identifié par un identifiant (login) et authentifié par un
mot de passe
 - est identifié sur le système par un numéro d’utilisateur (user
id)
  - possède un répertoire de travail propre (home)
  - utilise un shell personnel permettant l’exécution des
commandes au cours de sa session
Un groupe d’utilisateurs :
  - est défini par un nom et un numéro de groupe (group id)
  - permet de définir des mêmes droits pour les membres du groupe



Les **fichiers de configuration** des utilisateurs contiennent des informations critiques sur les utilisateurs.
**/etc/shadow**, par exemple, **stocke les mots de passe de manière chiffrée**. Si un attaquant y accède, il peut
tenter de les casser via un outil de force brute.
Les fichiers **.bashrc, .profile** et **/etc/passwd** contiennent des configurations importantes. Un attaquant qui
modifie ces fichiers peut **exécuter des commandes malveillantes** au démarrage d’une session.

# Répertoire

**Qu'est-ce que ~/.bashrc ?**

Le fichier **.bashrc** est un **script de configuration** qui est exécuté chaque fois qu'un
**terminal interactif** est lancé sous Bash (Bourne Again SHell). Il permet de
personnaliser l'environnement du terminal, notamment en définissant des alias,
en modifiant **l'affichage du prompt**, en exportant des **variables d'environnement**
et en exécutant des **commandes spécifiques** à l'ouverture d'une session.
Si on veux l'historique du bash dans /.bash_histoy ou /home/utilisateur/bash_histoy

**Qu'est-ce que ~/.profile ?**

Le fichier **.profile** est un script de configuration exécuté lors de la connexion d'un utilisateur sur un shell de
type login shell (ex. lorsqu'on ouvre une session en SSH ou une console TTY). Il sert principalement à :
- Configurer l'environnement utilisateur (variables d'environnement, alias, etc.)
- Lancer des commandes au démarrage de la session
- Définir le chemin du shell et des fichiers de configuration
- Personnaliser l'expérience utilisateur (prompt, historique, etc.)

 **Qu'est-ce que /etc/shadow ?**
Ce fichier contient les mots de passe chiffrés des utilisateurs et d'autres
informations liées à la sécurité des comptes. **Il ne peut être éditer qu’avec
une élévation de privilège**.



# Commande

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

- **Changer Password**
  
_modifier le mots de passe _
  
```bash 
passwd nom
```
necessite d'etre sur le user ou etre root

-e invalide le mots et oblige l'utilisateur a utiliser un nouveau mdp

-l supprime le mots de pass = utilisateur ne paut plus se co 

-S information sur le mot de passe avec -a all

---

- **Information compte**
  
_permet d'avoir des info sur un compte _
  
```bash 
id nom
```

---

- **Céer un groupe**
  
_créer un groupe _
  
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

- Penser a remove le groupe Users


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

