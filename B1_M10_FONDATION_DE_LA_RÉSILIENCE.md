# **FONDATION DE LA RÉSILIENCE**

## A comprendre 
- Comprendre les concepts fondamentaux du stockage et de la redondance.
- Identifier les différents types d'architectures de stockage (DAS, NAS, SAN, Cloud).
- Différencier les architectures locales, distantes et hybrides.
- Comprendre l'intérêt de la redondance physique des systèmes et des données.
- Appréhender les mécanismes RAID et savoir les configurer sous différents systèmes d'exploitation.
- Illustrer par des cas concrets et des exemples d'actualité l'importance du stockage dans la résilience.


## LE STOCKAGE

**Le stockage** fait référence à l'ensemble des méthodes, dispositifs et technologies utilisés pour conserver les
données numériques de façon durable, accessible et sécurisée. Il peut s'agir de supports physiques
(disques durs, SSD, bandes magétiques) ou virtuels (cloud), adaptés aux besoins en performance, capacité,
coût et disponibilité.

**Une stratégie de stockage efficace vise à assurer la conservation intègre des données en toute circons-
tance, y compris lors d'un sinistre ou d'une cyberattaque.**


**DIFFERENT TYPE DE STOCKAGE :**

*Peux etre utile : https://www.youtube.com/watch?v=uT7uvxlyxeA*

Il esiste plusieurs **supports de stockages**, associés à des modes de stockage de la données et des utilisations spéci-
fiques :
- **DAS (Direct Attached Storage) :** stockage directement connecté au serveur (ex: disque dur externe)
en mode blocs, pas accessible par le réseau.
- **NAS (Network Attached Storage) :** unité de stockage connectée via réseau, partagée entre plu-
sieurs utilisateurs en mode fichiers.Une PME utilise un NAS pour centraliser les sauvegardes de tous
ses ordinateur.
- **SAN (Storage Area Network) :** réseau spécialisé dédié au stockage, utilisé en entreprise pour per-
formances élevées, en mode blocs.Une multinationale utilise SAN pour ses bases de données cri-
tiques. il sont monté sur un ordi comme un disque réel mais de facon distant, le disque ne sera accessibles que a la machine a laquelle il sera associé (disque delocalisé)
- **Cloud Storage :** stockage mutualisé sur des serveurs distants, administré par un tiers (AWS S3,
Azure Blob, Google Cloud).

