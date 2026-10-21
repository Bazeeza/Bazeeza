<p align="center">
  <img src="assets/banniere.svg" width="100%" alt="Bariu Azeez — Technicien réseau et télécommunication · Réseaux Cisco, téléphonie IP, supervision, infrastructure"/>
</p>

<p align="center">
  <a href="mailto:Azeez@bazeeza.ca"><img src="https://img.shields.io/badge/Courriel-Azeez%40bazeeza.ca-2b9dff?style=flat-square&logo=maildotru&logoColor=white" alt="Courriel"/></a>
  <img src="https://img.shields.io/badge/Montréal-QC-3fe0a0?style=flat-square&logo=googlemaps&logoColor=white" alt="Montréal, QC"/>
  <img src="https://img.shields.io/badge/Langues-Français%20·%20English-c792ea?style=flat-square" alt="Français et anglais"/>
</p>

<p align="center">
  <b>Finissant du DEC en Techniques de l'informatique, profil réseautique</b> (Collège de Rosemont).<br>
  En parallèle, <b>40 h/semaine en centre de données</b> (opérations 24/7) depuis 2023.<br>
  Je monte des réseaux, je les supervise, et je documente tout pour qu'un autre technicien puisse le refaire.
</p>

<p align="center">
  <img src="assets/chiffres.svg" width="100%" alt="2 serveurs en production sur 2 continents · 284 000+ tentatives d'intrusion bloquées, 0 réussie · 1 450 lignes de scripts de durcissement CIS · 50+ procédures documentées"/>
</p>

---

## Projets phares

### 1 · Infrastructure personnelle en production, sur deux continents

Deux serveurs Linux (Canada et Finlande) que j'administre seul, reliés par un **réseau privé maillé** : aucun port d'administration exposé sur Internet. Chaque serveur a un rôle distinct, et le second **surveille le premier** toutes les 2 minutes pour m'alerter en cas de panne.

<p align="center">
  <img src="assets/infra.svg" width="100%" alt="Schéma : poste d'administration, nœud A au Canada (gestion à distance, supervision), nœud B en Finlande (automatisation, veille croisée), bot Telegram en lecture seule"/>
</p>

- **Sécurité** : SSH par clé seulement, pare-feu `ufw` et `fail2ban` (plus de 284 000 tentatives bloquées, aucune intrusion), services Docker limités à `127.0.0.1` parce que Docker contourne le pare-feu.
- **Supervision** : Uptime Kuma (9 sondes) et Beszel pour les métriques, alertes sur Telegram.
- **Bot de supervision** : la commande `/etat` sur Telegram donne l'état des services. Le relais est un service `systemd` durci (système en lecture seule, utilisateur dynamique, 64 Mo max). Il **n'ouvre aucun port** (connexion sortante uniquement) et ne lit les données qu'en lecture seule.
- **Méthode** : sauvegarde avant chaque modification, commande de retour en arrière prévue avant d'appliquer un changement.

`Linux` `Tailscale / WireGuard` `Docker` `systemd` `Python` `n8n` `ufw` `fail2ban` `Cloudflare Tunnel`

### 2 · Réseau Cisco redondant entre deux bâtiments

Si le lien principal tombe, le trafic bascule **automatiquement** par un routeur de secours, sans protocole de routage dynamique : des **routes statiques flottantes** (distance administrative 1 contre 5). Inclut le routage inter-VLAN, le router-on-a-stick et un VLAN « trou noir » pour les ports inutilisés.

`Cisco IOS` `VLAN 802.1Q` `Routage statique` `Distance administrative` `Commutateur L3` · [**Voir la documentation**](https://github.com/Bazeeza/Projets-Runbooks/tree/main/420-H66-RO%20PROJETS-R%C3%89SEAUTIQUE-2/Route-ST)

### 3 · Durcissement automatisé selon le CIS Benchmark

Deux scripts qui **vérifient puis corrigent** la configuration de sécurité d'un poste à partir d'un fichier XML : Ubuntu 24.04 en Bash (560 lignes) et Windows 11 en PowerShell (519 lignes). Un mode validation produit un rapport sans rien modifier, et un mode correction applique les valeurs recommandées (paquets, `sysctl`, services, comptes, journalisation).

`Bash` `PowerShell` `CIS Benchmark` `XML` · [**Voir les scripts**](https://github.com/Bazeeza/Projets-Runbooks/tree/main/420-H34-RO%20UTILITAIRES-R%C3%89SEAUX-AVANC%C3%89S/TP2_CIS)

### 4 · Supervision d'un réseau sur équipements physiques

Réseau Cisco physique (VLAN, DHCP avec relais, NAT) supervisé par **SNMP** et **Zabbix** : serveur sous AlmaLinux, agents Linux et Windows, déclencheurs avec des seuils *warning* et *critical* justifiés.

`Zabbix` `SNMP v2c` `AlmaLinux` `Cisco` · [**Voir les procédures**](https://github.com/Bazeeza/Projets-Runbooks/tree/main/420-H63-RO%20SUPERVISION-R%C3%89SEAUX-LOCAUX)

### 5 · Services déployés sur AWS avec Terraform

Infrastructure décrite en code : VPC, instances EC2 et conteneurs Docker pour le gestionnaire de mots de passe Vaultwarden et la messagerie Mattermost. En équipe, j'ai aussi déployé GLPI, Nextcloud et RDS MySQL, supervisés avec CloudWatch.

`Terraform` `AWS EC2 / VPC / RDS` `CloudWatch` `Docker` · [**AutomationHub**](https://github.com/Bazeeza/AutomationHub) · [**Services Internet**](https://github.com/Bazeeza/Projets-Runbooks/tree/main/420-H66-RO%20POJET-SRV-INTERNET-3)

---

## Compétences

**Réseau et télécom**

<p align="left">
  <img src="https://img.shields.io/badge/Cisco%20IOS-1BA0D7?style=for-the-badge&logo=cisco&logoColor=white" alt="Cisco IOS"/>
  <img src="https://img.shields.io/badge/VLAN%20·%20OSPF%20·%20NAT%20·%20ACL-004170?style=for-the-badge" alt="VLAN, OSPF, NAT, ACL"/>
  <img src="https://img.shields.io/badge/FreePBX%20·%20SIP-31A34C?style=for-the-badge" alt="FreePBX, SIP"/>
  <img src="https://img.shields.io/badge/Wireshark-1679A7?style=for-the-badge&logo=wireshark&logoColor=white" alt="Wireshark"/>
  <img src="https://img.shields.io/badge/WireGuard%20·%20Tailscale-88171A?style=for-the-badge&logo=wireguard&logoColor=white" alt="WireGuard, Tailscale"/>
</p>

**Supervision et sécurité**

<p align="left">
  <img src="https://img.shields.io/badge/Zabbix-D40000?style=for-the-badge&logo=zabbix&logoColor=white" alt="Zabbix"/>
  <img src="https://img.shields.io/badge/SNMP-5C2D91?style=for-the-badge" alt="SNMP"/>
  <img src="https://img.shields.io/badge/Uptime%20Kuma-5CDD8B?style=for-the-badge&logo=uptimekuma&logoColor=white" alt="Uptime Kuma"/>
  <img src="https://img.shields.io/badge/CIS%20Benchmark-2B3A55?style=for-the-badge" alt="CIS Benchmark"/>
  <img src="https://img.shields.io/badge/fail2ban%20·%20ufw-444444?style=for-the-badge" alt="fail2ban, ufw"/>
</p>

**Systèmes, cloud et automatisation**

<p align="left">
  <img src="https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black" alt="Linux"/>
  <img src="https://img.shields.io/badge/Windows%20Server-0078D6?style=for-the-badge&logo=windows&logoColor=white" alt="Windows Server"/>
  <img src="https://img.shields.io/badge/Proxmox-E57000?style=for-the-badge&logo=proxmox&logoColor=white" alt="Proxmox"/>
  <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white" alt="AWS"/>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=for-the-badge&logo=terraform&logoColor=white" alt="Terraform"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Bash%20·%20PowerShell%20·%20Python-1F2937?style=for-the-badge&logo=gnubash&logoColor=white" alt="Bash, PowerShell, Python"/>
</p>

---

## Parcours

| Période | |
|---|---|
| **2023 – aujourd'hui** | **Centre de données**, opérations 24/7 : environnement critique, procédures strictes, santé et sécurité |
| **En cours (dernière année)** | **DEC en Techniques de l'informatique, profil réseautique**, Collège de Rosemont : Cisco, supervision, services Internet, sécurité, virtualisation |

---

<p align="center">
  <b>Je cherche un poste de technicien en télécommunication ou en réseau dans la région de Montréal.</b><br>
  CV sur demande : <a href="mailto:Azeez@bazeeza.ca?subject=Demande%20de%20CV">Azeez@bazeeza.ca</a>
</p>
