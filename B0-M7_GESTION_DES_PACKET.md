# Gestion des packets
## Mise a jours

 - Rechercher le mise à jours
```
apt update
```

 - afficher la liste des paquets disposant d’une mise à
jour
 
```
apt list --upgradable
```

- installer les mise a jours

```
apt upgrade 
```

_Retrouver les liens vers les depots logiciels pour trouver les mises a jours_

etc/apt/sources.list

---

## Instalasion

-Rechercher un logiciel(pas necessaire si on connait deja le nom)

```
apt search nom
```

-Installer un logiciel 

```
apt install nom
```
indtall dans /bin et peux etre lancer dirrectement en tapant son nom hors root 

-affiche tout les packet 

```
dpkg -l 
```

## desinstalation

```
apt remove nom
```
_remove les packet mais garde les configs et les dependanse_
```
apt purge nom
```
_clean mais garde les dépendances_

```
apt autoremove nom
```
_clean mais garde les dépendances_
