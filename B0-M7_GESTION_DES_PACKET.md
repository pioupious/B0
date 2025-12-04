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

- Mise ajours ciblée
```
apt upgrade --only-upgrade nom
```

- Mis a jours distribution installée
```
apt full-upgrade
```
- Mis a niveau distribution installée
```
apt dist upgrade
```

## Instalasion

- Rechercher un logiciel(pas necessaire si on connait deja le nom)

```
apt search nom
```

- Installer un logiciel 

```
apt install nom
```
install dans /bin et peux etre lancer dirrectement en tappant son nom hors root 

- Installer un .deb

_ans /tmp_
```
wget ....
```
_si necessaire renomer le point deb_

```
mv old.deb new.deb
```

_executer avec le droit debian pour l'instalation_

```
dpkg -i
```

_si packet manquant_

```
apt --fix-broken install
``` 
-affiche tout les packet sur l'ordi

```
dpkg -l 
```



-**mise ne place d'un lien de mise à jours (exemple google)**

_télécharger le clée publique dans le repertoir /etc/apt/keyring_

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
deb [signed-by=/etc/apt/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main
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

## Netoyage 
_nettoyage du cache_
```
apt autoclean 
```
_suppression des paquets inutiles_
```
apt autoremove
```

## Horloge 

_voir l'heure instant T_

```
timedatectl
```

_voir info sur l'horloge_

```
timedatectl timesync-status
```
_parmatrage l'horloge modifier /etc/systemd/timesyncd.conf et ajouter liens server horloge dans NTP exemple : ntp.univ-rennes2.fr
et decomenter FallbackNTP_

_activer le NTP_

```
timedatectl set-ntp true
```

_puis restart  le systeme de synchro_

```
systemctl restart systemd-timesyncd
```

_liste des différent fuseau horraire_

```
timedatectl list-timezones
```

_liste des différent fuseau horraire_

```
timedatectl set-timezone (zone ex:Europe/Paris) 
```
