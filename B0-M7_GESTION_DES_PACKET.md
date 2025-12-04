# Gestion des packets
## Mise a jours

 - Rechercher le mise à jours
```
apt update
```

 - Afficher la liste des paquets disposant d’une mise à
jour
 
```
apt list --upgradable
```

- Installer les mises à jours

```
apt upgrade 
```

---

_Retrouver les liens vers les depots logiciels pour trouver les mises à jours_

etc/apt/sources.list

---


- Mise à jours ciblée
```
apt upgrade --only-upgrade nom
```

- Mise à jours distribution installée
```
apt full-upgrade
```
- Mise à niveau distribution installée
```
apt dist-upgrade
```

## Installation

- Rechercher un logiciel(pas necessaire si on connait deja le nom)

```
apt search nom
```

- Installer un logiciel 

```
apt install nom
```
_install dans /bin et peux etre lancer dirrectement en tappant son nom hors root_

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
dpkg -i *.deb
```

_si packet manquant_

```
apt --fix-broken install
``` 
- Affiche tout les packet sur l'ordi

**Resume** 
```
cd /tmp
wget ....
mv *=deb new.deb
dpkg -i *.deb
(apt --fix-broken install)
```

```
dpkg -l 
```

-**Mise ne place d'un lien de mise à jours (exemple google)**

_Télécharger le clée publique dans le repertoir /etc/apt/keyrings_

```
wget https://dl.google.com/linux/linux_signing_key.pub
```
_Rename la clée_

```
mv linux_signing_key.pub google-key.pub
```
_Convertir la clée_
```
gpg --dearmor google-key.pub > google-key.gpg
```
_Dans le répertoire /etc/apt/sources.list.d/ creér file nomapp.list_

```
deb [signed-by=/etc/apt/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main
```
(deb signer avec la clée trouvable ici dans hhtp)

**Resume**
```
cd /etc/apt/keyrings
wget https://dl.google.com/linux/linux_signing_key.pub
mv linux_signing_key.pub google-key.pub
gpg --dearmor google-key.pub > google-key.gpg
echo "deb [signed-by=/etc/apt/keyrings/google-key.pub.gpg] http://dl.google.com/linux/chrome/deb/ stable main" > /etc/apt/sources.list.d/google-chrome.list

```

_Puis installer google_

```
apt intall google-chrome-stable
```


 
## desinstallation

```
apt remove nom
```
_Remove les packet mais garde les configs et les dependanse_
```
apt purge nom
```
_Clean mais garde les dépendances_

```
apt autoremove nom
```
_Clean tout_

## Netoyage 

_Nettoyage du cache_
```
apt autoclean 
```
_Suppression des paquets inutiles_
```
apt autoremove
```

## Horloge 

_Voir l'heure instant T_

```
timedatectl
```

_Voir info sur l'horloge_

```
timedatectl timesync-status
```
_Parmetrage l'horloge modifier /etc/systemd/timesyncd.conf et ajouter liens server horloge dans NTP exemple : ntp.univ-rennes2.fr
et decommenter FallbackNTP_

_Activer le NTP_

```
timedatectl set-ntp true
```

_Puis restart  le systeme de synchro_

```
systemctl restart systemd-timesyncd
```

_Liste des différent fuseau horraire_

```
timedatectl list-timezones
```

_liste des différent fuseau horraire_

```
timedatectl set-timezone (zone ex:Europe/Paris) 
```
