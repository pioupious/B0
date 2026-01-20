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
--------------------------------------------------------
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

**Typologie des Stockages**
----------------------------------------------------
!!*https://urlr.me/YD-jHBVB* !!

Les différents mode de stockage de la donnée :les blocs, les fichiers et les objets. 

**Le stockage en blocs :** Il divise les données en blocs de taille fixe et les stocke individuellement avec une
faible latence, idéal pour les bases de données et les systèmes de fichiers haute performance.

**Le stockage en fichiers :** Il permer d'organiser les données sous forme de fichiers hiérarchisés dans des dos-
siers, comme sur un disque dur classique, adapté au partage de fichiers et aux systèmes NAS.

**Le stockage en objets :** Stocke les données sous forme de données brutes avec métadonnées et identifiants
uniques, optimisé pour l’évolutivité et l’accès via Internet, typique du cloud (comme Amazon S3).

**Les architectures liées au stockage : Locale, Distante, Hybride**
--------------------------------------------------------

- **Locale :** données stockées sur site (serveurs internes), maîtrise de la connaissances du SI.
- **Distante :** données externalisées chez un prestataire ou dans le cloud, perte de la connaissance et
de la maîtrise du SI.
- **Hybride :** combinaison des deux, souvent pour des raisons de performance, coût et sécurité, diffu-
sion de la connaissance du SI.

**Solutions :**
- Veeam, Rubrik, Commvault pour sauvegarde hybride.
- Cloud-native storage (Azure Files, AWS EFS).

**Cas concret :**
- Une startup sauvegarde localement ses données critiques et réplique automatiquement sur AWS
(modèle hybride).
- TV5 qui perd une partie de la maîtrise de son SI en externalisant.




