---
marp: true
theme: default
style: |
  section {background-color: #121114}
  h1,h2,h3 {color: #8393f0}
  p,ul,li,td,th {color: #ccc}
  section table {font-size: 0.85em}
  section table td {background-color: #121114}
  section table th {background-color: #272133; font-weight: bolder}
  pre {background-color: #17151a; color: #ccc}
  blockquote {border: 2px green solid; border-left-width: 15px; padding: 0.5em 15px;font-style: italic }
paginate: true
header: "Découverte de la virtualisation"
footer: "![height:20px](https://raw.githubusercontent.com/DiginamicInternal/PublicAssets/refs/heads/main/Logo-diginamic-color-blk.png)"
---

# Découverte de la virtualisation

### Concepts fondamentaux

Nicolas SAHUC

---

## 🎯 Objectifs pédagogiques

1. Définir la virtualisation, ses avantages et ses limites
2. Distinguer hyperviseurs de type 1 et de type 2
3. Employer le vocabulaire : hôte, VM, vCPU, datastore, cluster, HA, FT…
4. Différencier SAN et NAS, comprendre le réseau virtuel
5. Présenter la VDI et les modèles IaaS, PaaS, SaaS

---

## Le parcours

| #  | Étape                                    | Durée  |
|----|------------------------------------------|--------|
| 01 | La virtualisation : généralités          | 1 h 30 |
| 02 | Virtualisation de serveurs               | 2 h    |
| 03 | Virtualisation du stockage et du réseau  | 1 h 30 |
| 04 | VDI et cloud computing                   | 1 h 30 |

---

# 1. Généralités

---

## Qu'est-ce que la virtualisation ?

Exécuter, sur une **machine hôte** (hyperviseur), un ou plusieurs systèmes d'exploitation installés dans des **machines virtuelles** (VM).

> Chaque VM croit disposer de son propre matériel : l'hyperviseur partage les ressources réelles.

---

## Avantages / inconvénients

| Avantages | Inconvénients |
|---|---|
| Mutualisation des ressources | Coûts initiaux (matériel, licences) |
| Fin de la sous-utilisation des serveurs | *Overhead* de gestion |
| Énergie, climatisation mutualisées | Performances impactées par les VM voisines |
| Flexibilité, sauvegardes facilitées | |
| Économies à long terme | |

---

## Bien choisir sa solution

- Identifier correctement le **besoin**
- Choisir sa **supervision** et ses **licences**
- **Dimensionner** et anticiper les évolutions
- Rester **indépendant** de la technologie choisie

---

## Hyperviseurs : type 1 vs type 2

| | Type 1 — *bare metal* | Type 2 — hébergé |
|---|---|---|
| Installé sur | le matériel | un OS hôte |
| Usage | infrastructure d'entreprise | test, poste de travail |
| Performances | élevées | limitées |
| Exemples | ESXi, Hyper-V, KVM, Proxmox, XenServer | VirtualBox, VMware Workstation, Parallels |

---

## Le cluster d'hyperviseurs

- **Failover** : basculement si un nœud tombe
- **Load-balancing** : répartition de la charge
- **Migration** à froid ou à chaud des VM, entre nœuds ou entre datastores
- **HA** : haute disponibilité des services

---

# 2. Virtualisation de serveurs

---

## Terminologie

| Terme | Sens |
|---|---|
| Hôte | serveur physique |
| Hyperviseur | logiciel qui exécute les VM |
| VMM | composant de gestion des VM |
| Datastore | conteneur logique de stockage |
| vCPU / vRAM | CPU / RAM attribués à une VM |
| Nœud | membre d'un cluster |

---

## Optimiser

- **Concentration** : plus de serveurs dans moins d'espace
- **Consolidation** : meilleur taux d'utilisation de chaque serveur
- **Rationalisation** : suppression du superflu
- **Hyperconvergence** : calcul + stockage + réseau agrégés
- **Provisionnement dynamique**, **surallocation**

> La surallocation est un pari : il se pilote avec de la supervision.

---

## Disponibilité

| | HA | FT |
|---|---|---|
| Principe | redémarrage sur un autre hôte | VM exécutée en double |
| Interruption | courte | aucune |
| Coût | faible | double ressources |

Failover **actif/actif** (répartition) ou **actif/passif** (veille répliquée)

---

## Le vocabulaire VMware

- **vMotion** : migration à chaud d'une VM entre hôtes
- **Storage vMotion** : migration à chaud des disques entre datastores
- **DRS** : répartition automatique des VM (via vMotion)
- **Storage DRS** : répartition automatique des disques

---

# 3. Stockage et réseau

---

## Virtualiser le stockage

*Software-Defined Storage* : un **pool** unique de baies hétérogènes

- Fibre Channel : réseau de stockage très haut débit dédié
- iSCSI : commandes SCSI transportées sur IP
- SAS : disques hautes performances en série

---

## SAN ou NAS ?

| | SAN | NAS |
|---|---|---|
| Le client voit | des **blocs** (un disque) | des **fichiers** (un partage) |
| Protocoles | Fibre Channel, iSCSI | SMB, NFS |
| Usage | datastores de virtualisation | partage de fichiers |

---

## Virtualiser le réseau

Une implémentation **logicielle** du réseau : vSwitch, routeurs virtuels, VLAN

- Configuration et sécurité centralisées
- VLAN simplifiés
- Routage sans matériel supplémentaire
- Flexibilité

---

# 4. VDI et cloud

---

## VDI — Virtual Desktop Infrastructure

Le poste de travail tourne sur l'infrastructure, accessible depuis **n'importe quel terminal**.

| ✔ | ✘ |
|---|---|
| Sécurité centralisée | Hyperviseurs critiques |
| Administration facilitée | Dépendance à une solution |
| Coûts réduits à long terme | Investissement initial |

---

## Cloud computing

Délocalisation de l'infrastructure, des applications ou des données chez un opérateur.

- ✔ mutualisation, haute disponibilité, accès partout, évolutivité, SLA
- ✘ confidentialité, dépendance au fournisseur et au lien internet

---

## IaaS, PaaS, SaaS

| Modèle | On loue | On gère |
|---|---|---|
| IaaS | des serveurs | OS, applis, données |
| PaaS | une plateforme | applis, données |
| SaaS | un logiciel | ses données |

---

# Des questions ?

Pour toute question [adressez-vous au service pédagogie](mailto:pedagogie@diginamic.fr)
