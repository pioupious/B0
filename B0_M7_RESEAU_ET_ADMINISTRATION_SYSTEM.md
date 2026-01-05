# RESEAU ET ADMINISTRATION SYSTEM

| Commande      | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| `ip a`         | Afficher les informations des cartes réseaux |
| `ip route`         | Afficher les informations default gateaway |
| `ping`         | Interpel un terminal cible -c (count) nombre de ping |
| ` nslookup`         | Pour connaître le DNS qui résous les URL|

## Changer ip et DHCP

**Linux Shell**

```bash

nano /etc/network/interfaces

iface ens33 inet static
                  address 192.168.1.2/24
                  gateway 192.168.1.254

ou

iface ens33 inet dhcp


```
**Linux Classic**

- Cliquer sur l'icône des deux PC en haut à droite, puis modifier les connexions et double clic
sur wired connection 1. Sélectionnez DHCP et enregistrez. Désactivez et Activez le réseau.
