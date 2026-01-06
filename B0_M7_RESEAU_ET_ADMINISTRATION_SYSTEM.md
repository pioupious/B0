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

## Analyse Reseau 

| Commande      | Description                                                                                     |
|---------------|-------------------------------------------------------------------------------------------------|
| `ss`         | afficher des informations sur les connexions réseau actives (  Identifier les connexions établies et les ports ouverts Détecter des connexions suspectes ou malveillantes Diagnostiquer des problèmes de réseau et d’applications) |
| `Nmap`         | permet de découvrir les hôtes,services et ports ouverts sur un réseau ( Effectuer un scan des ports pour détecter des services vulnérables Identifier les systèmes et leurs versions pour évaluer les failles potentielles Tester la robustesse des pare-feux et des IDS/IPS (systèmes de détection d’intrusion)|

** Utiliser Wireshark pour les distribution graphique et Tshark pour les shells 
