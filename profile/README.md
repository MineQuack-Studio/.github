<div align="center">

# Xeinoria Studio

<sub><i>Réseau Minecraft francophone — un seul cluster, plusieurs mondes.</i></sub>

[Discord](https://discord.gg/8gFKV3Pr7E) ·
[Site](https://norath.fr) ·
[Signaler un bug / Proposer une idée](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) ·
[Licence CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

</div>

---

> **Un bug ? Une idée ? Une question ?**
> Tout passe par [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) pour ouvrir une issue, peu importe le serveur ou le composant.

---

Xeinoria est un réseau Minecraft Paper/Velocity propulsé par [Skript](https://skriptlang.org) et des serveurs minecraft backend sous [Paper](https://papermc.io/).
Cette organisation regroupe tout le code et la configuration du réseau : scripts gameplay, configs serveurs, environnement de dev, frontend web, infra.

## Carte des dépôts

### Scripts gameplay (Skript)

| Dépôt | Rôle |
|---|---|
| [`xeinoria-scripts-global`](https://github.com/Xeinoria-Studio/xeinoria-scripts-global) | Scripts partagés par tous les serveurs (friends, party, vanish, claim-bluemap…). Inclus comme sous-module dans chaque serveur. |
| [`xeinoria-server-hub`](https://github.com/Xeinoria-Studio/xeinoria-server-hub) | Scripts spécifiques au Hub (lobby, NPC, sélecteur de serveurs). |
| [`xeinoria-server-survie`](https://github.com/Xeinoria-Studio/xeinoria-server-survie) | Scripts spécifiques à la Survie (claims, export carte, gameplay). |
| [`xeinoria-server-crea`](https://github.com/Xeinoria-Studio/xeinoria-server-crea) | Scripts spécifiques au Créatif (plots, build tools). |
| [`xeinoria-server-nwland`](https://github.com/Xeinoria-Studio/xeinoria-server-nwland) | Scripts spécifiques à Norath World (events temporaires). |
| [`xeinoria-server-test`](https://github.com/Xeinoria-Studio/xeinoria-server-test) | Bac à sable des devs. |

### Configuration et infra

| Dépôt | Rôle |
|---|---|
| [`xeinoria-server-configs`](https://github.com/Xeinoria-Studio/xeinoria-server-configs) | Config Paper de chaque serveur (`server.properties`, `bukkit.yml`, `spigot.yml`, icônes, etc.). |
| [`xeinoria-proxy`](https://github.com/Xeinoria-Studio/xeinoria-proxy) | Config du proxy Velocity : `velocity.toml`, MiniMOTD, Maintenance, icônes, traductions. |
| [`xeinoria-redis`](https://github.com/Xeinoria-Studio/xeinoria-redis) | Stack Redis (`docker-compose`) utilisée pour l'IPC inter-serveurs via SkRedis. |

### Outillage

| Dépôt | Rôle |
|---|---|
| [`xeinoria-dev-env`](https://github.com/Xeinoria-Studio/xeinoria-dev-env) | Environnement de dev local : image Docker Paper + plugins extras, tests automatiques, scripts de bootstrap. Idéal pour développer un Skript sans toucher la prod. |
| [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback) | Point d'entrée unique pour bugs, idées et questions des joueurs. |

