# Base de la virtualisation 

## Définition

_La virtualisation permet d'exécuter plusieurs systèmes d'exploitation sur une seule machine physique._
___
Idée clé de la virtualisation : _« Un ordinateur dans l’ordinateur. »_
L’hyperviseur pour chaque VM un disque virtuel qu’il verra son disque dur mais qui en réalité
est un simple fichier sur le disque réel.

## Histoire
Début avec des partitions logiques sur mainframes dans les années 60-70 (IBM) puis la virtualisation x86 dans les années 2000, et l'explosion du cloud dans les années 2010-2020.
## Avantages 
_La virtualisation optimise les ressources et améliore la sécurité._

- **Optimisation des ressources**

  * Un serveur physique est souvent sous-utilisé (5-15%).
  * Permet de consolider plusieurs serveurs sur un seul hôte, réduisant ainsi les coûts matériels, énergétiques et de maintenance.

- **Isolation et sécurité**

  * Sandbox pour analyser des malwares.
  * Environnements sécurisés pour développeurs.
  * Environnements séparés pour différents services (ex : serveur web + base de données sans cohabitation risquée).

- **Flexibilité / reproductibilité**
  * Snapshot / clones → revenir en arrière instantanément

- **Déploiement et Cloud**

  _Le cloud repose sur des hyperviseurs pour l'infrastructure_

  * Les services cloud (AWS, Azure, GCP) utilisent massivement la virtualisation.
  * Infrastructure as a Service (IaaS) et virtualisation réseau/stockage (SDN, SDS).
  * SDN permet une gestion centralisée et flexible du réseau, tandis que SDS gère le stockage indépendamment du matériel.
    
## Comprendre l'Hyperviseur

_L'hyperviseur exécute les machines virtuelles et gère les ressources._

  * Abstraction du CPU, gestion de la mémoire virtuelle et des périphériques.
  * Allocation dynamique des resources et isolation des environnements.

## Comparaison des Hyperviseurs Type 1 et Type 2
_Les hyperviseurs se divisent en deux types selon leur architecture._

* Type 1 (bare metal)

  _S'exécute directement sur le matériel_
  * Avantage : Offrant meilleure performance et sécurité. Egalement plus adpaté à de grandes structures (prends le pas sur l'os)
  * Default : Administration plus complexe, Nécessite une machine dédiée, Pas adapté aux postes utilisateurs classiques.
    
* Type 2 (hébergé)
  
  _S'exécute sur un OS hôte_
  * Avantages : plus simple à installer mais avec des performances inférieures.
  * Default : Performance inférieure (couches supplémentaires) , Dépend des ressources allouées par l’OS hôte

## Panorama des Solutions de Virtualisation

Différentes solutions existent pour la virtualisation :

   * VirtualBox : gratuit, open source, utilisé en formation, mais moins performant que VMware. ​
   * VMware Workstation Pro : solution professionnelle, stable et performante, idéale pour les laboratoires de cybersécurité. ​
   * Hyper-V : intégré à Windows, peut entrer en conflit avec d'autres hyperviseurs.

## Ressources Virtuelles

_Comprendre les ressources virtuelles est crucial pour la gestion des VMs_

* vCPU : unité de scheduling, peut être surprovisionné sans danger, mais peut causer latence.
* RAM virtuelle :
  * ballooning : l’hyperviseur récupère ou redonne de la RAM à une VM en fonction de ses besoins réels (réallocation
dynamique)
  * Swapping : lorsqu’il manque de RAM, une VM déplace temporairement des données vers le disque (plus lent)
  * Memory overcommit : on attribue plus de RAM virtuelle totale aux VM que la RAM physique disponible, en pariant que
tout ne sera pas utilisé simultanément
* Stockage virtuel : différents types de fichiers disques (VDI, VMDK, VHD/VHDX) et modes de provisionnement (statique vs dynamique).
   * VDI (VirtualBox)
   * VMDK (VMware)
   * VHD/VHDX (Hyper-V)
 
 ## Création d'une Machine Virtuelle
_Les formats d'image et d'exportation sont essentiels pour créer des VMs._

* Image ISO : fichier pour l'installation d'un OS.
* OVF : format standard pour décrire une VM, contenant plusieurs fichiers. ​
* OVA : archive compressée contenant un OVF, pratique pour partager des VMs préconfigurées.

# Synthèse de la mort qui tue 

* Virtualisation = abstraction du matériel
* Hyperviseurs type 1 vs type 2 → deux philosophies.
* Ressources virtuelles (vCPU, RAM, stockage) ≠ ressources physiques.
* Création d’une VM → comprendre ISO, OVF, OVA.
