<p align="center">
  <img src="assets/banniere.svg" width="100%" alt="Terminal : whoami → bazeeza ; intérêts : réseaux, téléphonie IP, supervision, homelab"/>
</p>

<p align="center">
  <a href="mailto:info@bazeeza.ca"><img src="https://img.shields.io/badge/info%40bazeeza.ca-0b1530?style=for-the-badge&logo=maildotru&logoColor=3fe0a0" alt="info@bazeeza.ca"/></a>
  <img src="https://img.shields.io/badge/Montréal-0b1530?style=for-the-badge&logo=googlemaps&logoColor=2b9dff" alt="Montréal"/>
  <img src="https://img.shields.io/badge/FR%20·%20EN-0b1530?style=for-the-badge&logo=googletranslate&logoColor=c792ea" alt="Français et anglais"/>
</p>

### Salut, moi c'est bazeeza

J'aime comprendre comment un paquet passe d'un point A à un point B, et surtout ce qui se passe quand il n'y arrive pas.

Le jour, je travaille dans un centre de données. Le reste du temps, je finis mon DEC en réseautique et je bricole mon propre lab : deux serveurs sur deux continents, un réseau maillé, de la supervision partout et un bot qui me prévient quand quelque chose tombe.

Tout ce que j'apprends finit en procédure écrite, pour que n'importe qui puisse le refaire.

---

## 🧪 Le lab

<p align="center">
  <img src="assets/infra.svg" width="100%" alt="Schéma : poste d'administration, nœud A au Canada (gestion à distance, supervision), nœud B en Finlande (automatisation, veille croisée), bot Telegram en lecture seule"/>
</p>

<p align="center">
  <img src="assets/lab-stats.svg" width="100%" alt="2 nœuds sur 2 continents · 9 sondes Uptime Kuma · 284 000+ tentatives bloquées, 0 intrusion · 0 port d'administration public"/>
</p>

**Ce que le lab m'a appris (parfois à la dure) :**

- **Docker contourne le pare-feu.** Une règle `ufw` ne protège pas un port publié par Docker : chaque service écoute donc sur `127.0.0.1`, et rien d'autre.
- **Un serveur en panne ne peut pas annoncer sa propre panne.** D'où la veille croisée : le nœud de Finlande vérifie celui du Canada toutes les 2 minutes.
- **Le port le plus sûr est celui qu'on n'ouvre pas.** Le bot `/etat` fonctionne en connexion sortante seulement : aucun port entrant.
- **On prévoit le retour en arrière avant d'appliquer le changement.** Sauvegarde d'abord, toujours.

