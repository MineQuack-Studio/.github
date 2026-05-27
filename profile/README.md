<div align="center">

# Xeinoria Studio

<sub><i>Réseau Minecraft francophone — un seul cluster, plusieurs mondes.</i></sub>

[Discord](https://discord.gg/xeinoria) ·
[Site](https://norath.fr) ·
[Signaler un bug / Proposer une idée](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) ·
[Licence CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

[English version below](#english)

</div>

---

> **Un bug ? Une idée ? Une question ?**
> Tout passe par [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) — c'est le seul endroit où ouvrir une issue, peu importe le serveur ou le composant. Les autres dépôts ont leurs issues désactivées pour éviter la dispersion. Les pull requests techniques restent sur le dépôt concerné.

---

Xeinoria est un réseau Minecraft Paper/Velocity propulsé par [Skript](https://skriptlang.org) et un proxy [Velocity](https://papermc.io/software/velocity). Cette organisation regroupe tout le code et la configuration du réseau : scripts gameplay, configs serveurs, environnement de dev, frontend web, infra.

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

Les variantes `…-private` (ex. [`xeinoria-server-survie-private`](https://github.com/Xeinoria-Studio/xeinoria-server-survie-private)) contiennent du code sensible (anti-cheat, intégrations payantes) et sont privées.

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
| [`xeinoria-web`](https://github.com/Xeinoria-Studio/xeinoria-web) | Frontend web ([norath.fr](https://norath.fr)). |
| [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback) | Point d'entrée unique pour bugs, idées et questions des joueurs. |

## Comment ça déploie

```
git push  ->  GitHub  ->  Webhook (push event)  ->  serveur Xeinoria  ->  sync fichiers
                                                                         (reload manuel par l'admin)
```

Chaque dépôt déclenche un webhook qui synchronise instantanément les fichiers concernés vers la prod. Les `/sk reload` (Skript) et les redémarrages (Paper/Velocity) restent manuels — on ne fait jamais rebooter un serveur sans intention.

## Pour les nouveaux contributeurs

1. Clonez [`xeinoria-dev-env`](https://github.com/Xeinoria-Studio/xeinoria-dev-env) et suivez son README pour avoir un serveur Paper local en moins de 5 minutes.
2. Forkez le dépôt du serveur sur lequel vous voulez bosser (ex. `xeinoria-server-survie`).
3. Ouvrez une PR — un mainteneur testera sur le serveur `test` avant merge.

## Licence

Sauf mention contraire dans le `LICENSE` d'un dépôt, tous les contenus sont sous [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).

---

<a id="english"></a>

# Xeinoria Studio (English)

<sub><i>French-speaking Minecraft network — one cluster, several worlds.</i></sub>

[Discord](https://discord.gg/xeinoria) ·
[Website](https://norath.fr) ·
[Report a bug / Suggest an idea](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) ·
[License CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)

---

> **A bug? An idea? A question?**
> Everything goes through [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback/issues/new/choose) — the single place to open an issue, no matter the server or component. Other repos have issues disabled to avoid scattering. Technical pull requests still belong to the repo they touch.

---

Xeinoria is a French-speaking Minecraft network running Paper back-ends behind a Velocity proxy, with most of the gameplay written in [Skript](https://skriptlang.org). This organization holds every piece of code and configuration that powers the network.

## Repository map

### Gameplay scripts (Skript)

| Repository | Role |
|---|---|
| [`xeinoria-scripts-global`](https://github.com/Xeinoria-Studio/xeinoria-scripts-global) | Scripts shared across every back-end (friends, party, vanish, claim-bluemap…). Included as a submodule by each server. |
| [`xeinoria-server-hub`](https://github.com/Xeinoria-Studio/xeinoria-server-hub) | Hub / lobby-specific scripts (NPCs, server selector). |
| [`xeinoria-server-survie`](https://github.com/Xeinoria-Studio/xeinoria-server-survie) | Survival-specific scripts (claims, map export, gameplay). |
| [`xeinoria-server-crea`](https://github.com/Xeinoria-Studio/xeinoria-server-crea) | Creative-specific scripts (plots, build tools). |
| [`xeinoria-server-nwland`](https://github.com/Xeinoria-Studio/xeinoria-server-nwland) | Norath World scripts (limited-time events). |
| [`xeinoria-server-test`](https://github.com/Xeinoria-Studio/xeinoria-server-test) | Dev sandbox. |

The matching `…-private` repos (e.g. [`xeinoria-server-survie-private`](https://github.com/Xeinoria-Studio/xeinoria-server-survie-private)) hold sensitive code (anti-cheat, paid integrations) and are private.

### Configuration and infra

| Repository | Role |
|---|---|
| [`xeinoria-server-configs`](https://github.com/Xeinoria-Studio/xeinoria-server-configs) | Paper configuration per server (`server.properties`, `bukkit.yml`, `spigot.yml`, server icons, etc.). |
| [`xeinoria-proxy`](https://github.com/Xeinoria-Studio/xeinoria-proxy) | Velocity proxy configuration: `velocity.toml`, MiniMOTD, Maintenance, icons, translations. |
| [`xeinoria-redis`](https://github.com/Xeinoria-Studio/xeinoria-redis) | Redis stack (`docker-compose`) used for cross-server IPC via SkRedis. |

### Tooling

| Repository | Role |
|---|---|
| [`xeinoria-dev-env`](https://github.com/Xeinoria-Studio/xeinoria-dev-env) | Local development environment: Docker Paper image, extra plugins, automated tests, bootstrap scripts. The right place to iterate on a Skript without touching production. |
| [`xeinoria-web`](https://github.com/Xeinoria-Studio/xeinoria-web) | Web frontend ([norath.fr](https://norath.fr)). |
| [`xeinoria-feedback`](https://github.com/Xeinoria-Studio/xeinoria-feedback) | Single entry point for player bug reports, ideas and questions. |

## Deployment flow

```
git push  ->  GitHub  ->  Webhook (push event)  ->  Xeinoria host  ->  file sync
                                                                       (manual reload by an admin)
```

Each repository triggers a webhook that instantly syncs the relevant files to production. Skript `/sk reload` and Paper/Velocity restarts stay manual — we never bounce a server without intent.

## New contributors

1. Clone [`xeinoria-dev-env`](https://github.com/Xeinoria-Studio/xeinoria-dev-env) and follow its README to spin up a local Paper server in under 5 minutes.
2. Fork the repository for the server you want to work on (e.g. `xeinoria-server-survie`).
3. Open a PR — a maintainer will test it on the `test` server before merging.

## License

Unless a per-repo `LICENSE` says otherwise, everything is published under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/).
