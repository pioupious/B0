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

# Commande

- **Créer un compte user**

_créer un user pose les questions plus simple_
  
```bash 
adduser jesuispierre
```

---

- **Add un compte user**

_add un user pause pas de question mais plus compliquer_
  
```bash 
useradd -d /home/pioupiouLove -m -g stagiaire -G sudo -u 1002 pioupiou2
```

- **Delet un user**
