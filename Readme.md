<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/Logo-diginamic-color-blk.png">
    <img src="assets/Logo-diginamic-color.svg" alt="Diginamic Formation" width="358">
  </picture>
</p>

# Découverte de la virtualisation

Concepts fondamentaux de la virtualisation : ce qu'elle apporte, les
hyperviseurs qui la rendent possible, son vocabulaire, et ses déclinaisons
— serveurs, stockage, réseau, postes de travail — jusqu'au cloud computing.

**Auteur :** Nicolas SAHUC <sahuc.nic@gmail.com>

## 🎯 Objectifs pédagogiques

À la fin de ce cours, vous saurez :

1. Définir la virtualisation et en citer les avantages, les inconvénients et les critères de choix.
2. Distinguer un hyperviseur de type 1 d'un hyperviseur de type 2, et citer des solutions de chaque type.
3. Employer le vocabulaire de la virtualisation de serveurs : hôte, VM, vCPU, datastore, cluster, HA, FT, vMotion…
4. Expliquer les objectifs de la virtualisation du stockage et du réseau, et différencier SAN et NAS.
5. Présenter la VDI et les trois grands modèles de cloud computing : IaaS, PaaS, SaaS.

## ❔ Pourquoi ce cours ?

La quasi-totalité des infrastructures d'entreprise repose aujourd'hui sur la
virtualisation : les serveurs y sont des machines virtuelles, le stockage est
mutualisé, le réseau est en partie logiciel, et le cloud n'est rien d'autre
qu'une virtualisation à très grande échelle opérée par un tiers. Maîtriser ces
notions est un prérequis pour administrer un système d'information moderne.

## Le parcours

Chaque étape est un fichier. On les suit **dans l'ordre** : chacune s'appuie sur la précédente.

| # | Étape | Durée | Ce qu'on y fait |
|---|---|---|---|
| [01](01-Generalites.md) | La virtualisation : généralités | 1 h 30 | définition, avantages et inconvénients, types de virtualisation, hyperviseurs de type 1 et 2, clusters |
| [02](02-Virtualisation-de-serveurs.md) | Virtualisation de serveurs | 2 h | terminologie (hôte, VM, VMM, vCPU…), concentration, consolidation, surallocation, HA, FT, vMotion, DRS |
| [03](03-Stockage-et-reseau.md) | Virtualisation du stockage et du réseau | 1 h 30 | Software-Defined Storage, Fibre Channel, iSCSI, SAS, SAN et NAS, réseau virtuel |
| [04](04-VDI-et-cloud-computing.md) | VDI et cloud computing | 1 h 30 | virtualisation de postes de travail, IaaS, PaaS, SaaS |
| [A](A-Glossaire.md) | Glossaire | — | les sigles du cours, en un coup d'œil |
