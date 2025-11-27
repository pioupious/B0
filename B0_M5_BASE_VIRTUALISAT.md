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

- *Optimisation des ressources*

  * Un serveur physique est souvent sous-utilisé (5-15%).
  * Permet de consolider plusieurs serveurs sur un seul hôte, réduisant ainsi les coûts matériels, énergétiques et de maintenance.

- *Isolation et sécurité*

  * Sandbox pour analyser des malwares.
  * Environnements sécurisés pour développeurs.
  * Environnements séparés pour différents services (ex : serveur web + base de données sans cohabitation risquée).

- *Flexibilité / reproductibilité*
  * Snapshot / clones → revenir en arrière instantanément

- *Déploiement et Cloud*

  _Le cloud repose sur des hyperviseurs pour l'infrastructure_

  * Les services cloud (AWS, Azure, GCP) utilisent massivement la virtualisation.
  * Infrastructure as a Service (IaaS) et virtualisation réseau/stockage (SDN, SDS).
  * SDN permet une gestion centralisée et flexible du réseau, tandis que SDS gère le stockage indépendamment du matériel.
    
# Comprendre l'Hyperviseur

_L'hyperviseur exécute les machines virtuelles et gère les ressources._

  * Abstraction du CPU, gestion de la mémoire virtuelle et des périphériques.
  * Allocation dynamique des resources et isolation des environnements.

# Comparaison des Hyperviseurs Type 1 et Type 2
_Les hyperviseurs se divisent en deux types selon leur architecture._

* Type 1 (bare metal)
  s'exécute directement sur le matériel_
  * Avantage : , offrant meilleure performance et sécurité. Egalement plus adpaté a de grandes structures (prends le pas sur l'os)
  * Default : 
*Type 2 (hébergé) : s'exécute sur un OS hôte, plus simple à installer mais avec des performances inférieures. 
