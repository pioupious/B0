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

-Mise ajours ciblée
```
apt upgrade --only-upgrade nom
```

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

-affiche tout les packet sur l'ordi

```
dpkg -l 
```

-**mise ne place d'un lien de mise à jours (exemple google)**

_télécharger le clée publique dans le repertoir /usr/share/keyring_

```
wget https://dl.google.com/linux/linux_signing_key.pub
```
_rename la clée_

```
mv linux_signing_key.pub google-key.pub
```
_convertir la clée _
```
gpg --dearmor google-key.pub > google-key.gpg
```
_dans le répertoire /etc/apt/sources.list.d/ creér file nomapp.list_

```
deb [signed-by=/usr/share/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main
```
(deb signer avec la clée trouvable ici dans hhtp)

_Puis installer google_

```
apt intall google-chrome-stable
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
