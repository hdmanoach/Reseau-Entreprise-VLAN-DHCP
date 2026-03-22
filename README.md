# Reseau-Entreprise-VLAN-DHCP

> Conception et déploiement d'une infrastructure réseau pour un nouveau site d'entreprise

![Cisco](https://img.shields.io/badge/Cisco-Packet%20Tracer-blue)
![VLAN](https://img.shields.io/badge/VLAN-802.1Q-green)
![DHCP](https://img.shields.io/badge/DHCP-Configured-orange)
![ACL](https://img.shields.io/badge/ACL-Security-red)

---

## Contexte

Dans le cadre de l'ouverture d'un nouveau bâtiment, une entreprise
doit mettre en place en urgence son infrastructure réseau suite à la
défaillance du prestataire externe initialement mandaté. À trois jours
de la mise en service, aucune configuration réseau n'est opérationnelle.

Le site doit accueillir plusieurs départements stratégiques avec des
besoins variés en connectivité, en performance et en sécurité. L'équipe
interne est chargée de concevoir et déployer une solution réseau fiable
dans un délai très contraint.

L'entreprise dispose d'un unique bloc d'adresses IP privées :
**192.168.10.0/24** (254 adresses utilisables), qui devra être
segmenté efficacement.

---

## Objectifs du projet

- Concevoir une architecture réseau adaptée aux besoins des départements
- Optimiser l'utilisation de l'espace d'adressage IP disponible
- Mettre en place un découpage logique du réseau (subnetting)
- Garantir la sécurité des données sensibles (notamment pour la Direction)
- Assurer la continuité de service dès l'ouverture du site
- Anticiper l'évolution future de certains services (notamment R&D)

---

## Périmètre

### Couvert par le projet
- La planification de l'adressage IP
- Le découpage en sous-réseaux (subnetting)
- La segmentation du réseau par département
- La définition des règles de base de sécurité réseau
- La préparation au déploiement physique et logique

### Hors périmètre
- L'installation physique détaillée (câblage, baie, etc.)
- La configuration avancée des serveurs applicatifs

---

## Besoins métiers

| Département | Postes | Caractéristiques | Croissance |
|---|---|---|---|
| Production | 100 | Machines industrielles incluses | Non mentionnée |
| R&D | 50 | Service en expansion | Oui — recrutements prévus |
| Comptabilité | 25 | Environnement stable | Non |
| Direction | 10 | Données sensibles, accès restreint | Non |
| **Total** | **185** | | |

---

## Plan d'adressage IP

| Département | VLAN | Sous-réseau | Masque | Plage utile | Broadcast | Capacité |
|---|---|---|---|---|---|---|
| Production | 10 | 192.168.10.0 | /25 | .1 → .126 | .127 | 126 |
| R&D | 20 | 192.168.10.128 | /26 | .129 → .190 | .191 | 62 |
| Comptabilité | 30 | 192.168.10.192 | /27 | .193 → .222 | .223 | 30 |
| Direction | 40 | 192.168.10.224 | /28 | .225 → .238 | .239 | 14 |

---

## Architecture réseau

image
---

## Contraintes

- **Délai très court** : mise en service sous 3 jours
- **Ressources limitées** : un seul bloc IP disponible
- **Évolutivité** : anticiper la croissance de la R&D
- **Sécurité** : isolation de la Direction et Comptabilité
- **Continuité** : service impératif dès le premier jour

---

## Livrables

- [x] Plan d'adressage IP détaillé
- [x] Schéma de segmentation réseau par sous-réseaux
- [x] Tableau de répartition des sous-réseaux par département
- [x] Documentation des choix techniques
- [x] Recommandations de sécurité réseau
- [x] Plan de déploiement simplifié
- [x] Simulation complète sur Cisco Packet Tracer
- [x] Configuration VLANs et Trunk 802.1Q
- [x] Routage inter-VLAN
- [x] Service DHCP par département
- [x] ACL de sécurité inter-VLANs
- [x] Adresses statiques imprimantes

---

## Résultats obtenus

| Test | Résultat |
|---|---|
| VLANs créés et actifs | ✅ Réussi |
| Trunk switch central | ✅ Réussi |
| Routage inter-VLAN | ✅ Réussi |
| Communication entre départements | ✅ Réussi |
| DHCP R&D, Compta, Direction | ✅ Réussi |

---

## Compétences mobilisées

- Subnetting et adressage IPv4
- Conception d'architecture réseau
- Configuration Cisco (VLANs, Trunk, ACL, DHCP)
- Analyse des besoins métiers
- Gestion de contraintes techniques
- Planification en environnement critique
- Notions de sécurité réseau

---

## Technologies utilisées

![Cisco](https://img.shields.io/badge/Cisco-2911%20%7C%202960-blue)
![Protocol](https://img.shields.io/badge/Protocol-802.1Q%20%7C%20IPv4-green)
![Tool](https://img.shields.io/badge/Tool-Packet%20Tracer-orange)
![Security](https://img.shields.io/badge/Security-ACL%20%7C%20VLAN-red)

---

## Auteur

**Manoach HOSSOU DODO**
Mars 2026
