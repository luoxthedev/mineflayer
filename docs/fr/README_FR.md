# Mineflayer

[![NPM version](https://badge.fury.io/js/mineflayer.svg)](http://badge.fury.io/js/mineflayer)
[![Build Status](https://github.com/PrismarineJS/mineflayer/workflows/CI/badge.svg)](https://github.com/PrismarineJS/mineflayer/actions?query=workflow%3A%22CI%22)
[![Discord](https://img.shields.io/badge/chat-on%20discord-brightgreen.svg)](https://discord.gg/GsEFRM8)
[![Gitter](https://img.shields.io/badge/chat-on%20gitter-brightgreen.svg)](https://gitter.im/PrismarineJS/general)
[![Irc](https://img.shields.io/badge/chat-on%20irc-brightgreen.svg)](https://irc.gitter.im/)
[![Issue Hunt](https://github.com/BoostIO/issuehunt-materials/blob/master/v1/issuehunt-shield-v1.svg)](https://issuehunt.io/r/PrismarineJS/mineflayer)

[![Try it on gitpod](https://img.shields.io/badge/try-on%20gitpod-brightgreen.svg)](https://gitpod.io/#https://github.com/PrismarineJS/mineflayer)

| <sub>EN</sub> [Anglais](../README.md) | <sub>RU</sub> [Russe](../ru/README_RU.md) | <sub>ES</sub> [Espagnol](../es/README_ES.md) | <sub>FR</sub> [Français](README_FR.md) | <sub>TR</sub> [Türkçe](../tr/README_TR.md) | <sub>ZH</sub> [Chinois](../zh/README_ZH_CN.md) | <sub>BR</sub> [Portuguese](../br/README_BR.md) |
|-------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|----------------------------|

Créer des robots Minecraft avec une API stable, puissante et de haut niveau en JavaScript, également utilisable depuis Python.

Si c'est la première fois que vous utilisez Node.js, vous devriez commencer avec le [tutoriel](tutorial.md). Vous connaissez Python ? Consultez quelques [exemples Python](https://github.com/PrismarineJS/mineflayer/tree/master/examples/python) et essayez [Mineflayer sur Google Colab](https://colab.research.google.com/github/PrismarineJS/mineflayer/blob/master/docs/mineflayer.ipynb).

## Caractéristiques

 * Supporte Minecraft 1.8 à 1.21.11 (1.8, 1.9, 1.10, 1.11, 1.12, 1.13, 1.14, 1.15, 1.16, 1.17, 1.18, 1.19, 1.20, 1.21, 1.21.9, 1.21.11) <!--version-->
 * Reconnaissance et pistage des entités.
 * Connaissance des blocs. Vous pouvez interroger le monde autour de vous. Quelques millisecondes suffisent pour trouver n'importe quel bloc.
 * Physique et mouvement - gère toutes les boîtes de collision.
 * Attaquer des entités et utiliser des véhicules.
 * Gestion de l'inventaire.
 * Artisanat, coffres, distributeurs, tables d'enchantement.
 * Creuser et construire.
 * Diverses fonctionnalités telles que connaître vos points de vie ou s'il pleut.
 * Activer des blocs et utiliser des objets.
 * Chat.

### Feuille de route

 Consultez [cette page](https://github.com/PrismarineJS/mineflayer/wiki/Big-Prismarine-projects) pour voir quels sont nos projets actuels. 
 
## Installation

D'abord, installez Node.js >= 18 depuis [nodejs.org](https://nodejs.org/) puis :

```bash
npm install mineflayer
```

Pour mettre à jour mineflayer (ou n'importe quel package Node.js) et ses dépendances, utilisez :
```bash
npm update
```

## Documentation

| lien | description |
|---|---|
|[tutorial](tutorial.md) | Commencez avec Node.js et mineflayer |
| [FAQ.md](FAQ.md) | Vous avez une question ? Allez d'abord ici |
| **[api.md](api.md)** <br/>[unstable_api.md](unstable_api.md) | La référence complète de l'API |
| [history.md](history.md) | L'historique des changements de mineflayer |
| [examples/](https://github.com/PrismarineJS/mineflayer/tree/master/examples) | Consultez tous les exemples de mineflayer |


## Contribuer

Veuillez lire [CONTRIBUTING.md](CONTRIBUTING.md) et [prismarine-contribute](https://github.com/PrismarineJS/prismarine-contribute)

## Utilisation

**Vidéos**

Un tutoriel vidéo qui explique comment mettre en place un robot mineflayer est disponible [ici.](https://www.youtube.com/watch?v=ltWosy4Z0Kw)

Si vous voulez en apprendre plus, des video peuvent être trouvées [ici,](https://www.youtube.com/playlist?list=PLh_alXmxHmzGy3FKbo95AkPp5D8849PEV) et le code source correspondant peut être trouvé [ici.](https://github.com/TheDudeFromCI/Mineflayer-Youtube-Tutorials)

[<img src="https://img.youtube.com/vi/ltWosy4Z0Kw/0.jpg" alt="tutorial 1" width="200">](https://www.youtube.com/watch?v=ltWosy4Z0Kw)
[<img src="https://img.youtube.com/vi/UWGSf08wQSc/0.jpg" alt="tutorial 2" width="200">](https://www.youtube.com/watch?v=UWGSf08wQSc)
[<img src="https://img.youtube.com/vi/ssWE0kXDGJE/0.jpg" alt="tutorial 3" width="200">](https://www.youtube.com/watch?v=ssWE0kXDGJE)
[<img src="https://img.youtube.com/vi/walbRk20KYU/0.jpg" alt="tutorial 4" width="200">](https://www.youtube.com/watch?v=walbRk20KYU)

**Premiers pas**

Sans version spécifiée, la version du serveur sera devinée automatiquement.
Sans authentification spécifiée, le style d'authentification Mojang sera deviné.

### Exemple Echo
```js
const mineflayer = require('mineflayer')

const bot = mineflayer.createBot({
  host: 'localhost', // ip du serveur minecraft
  username: 'Bot', // nom d'utilisateur pour rejoindre si auth est `offline`, sinon un identifiant unique pour ce compte. Changez si vous voulez changer de compte
  auth: 'microsoft' // pour les serveurs en mode hors ligne, vous pouvez définir ceci à 'offline'
  // port: 25565,              // définir si vous avez besoin d'un port différent de 25565
  // version: false,           // définir uniquement si vous avez besoin d'une version spécifique ou d'un snapshot (par exemple : "1.8.9" ou "1.16.5"), sinon c'est défini automatiquement
  // password: '12345678'      // définir si vous voulez utiliser l'authentification par mot de passe (peut être peu fiable). Si spécifié, le `username` doit être un email
})

bot.on('chat', (username, message) => {
  if (username === bot.username) return
  bot.chat(message)
})

// Enregistrer les erreurs et les raisons de kick :
bot.on('kicked', console.log)
bot.on('error', console.log)
```

Si `auth` est défini sur `microsoft`, vous serez invité à vous connecter à microsoft.com avec un code dans votre navigateur. Après vous être connecté dans votre navigateur,
le bot obtiendra et mettra automatiquement en cache les jetons d'authentification (sous votre nom d'utilisateur spécifié) afin que vous n'ayez pas à vous reconnecter.

Pour changer de compte, mettez à jour le `username` fourni. Par défaut, les jetons mis en cache seront stockés dans le dossier .minecraft de votre utilisateur, ou si `profilesFolder` est spécifié, ils seront stockés là-bas à la place.
Pour plus d'informations sur les options du bot, consultez la [documentation API](https://github.com/PrismarineJS/node-minecraft-protocol/blob/master/docs/API.md#mccreateclientoptions) de node-minecraft-protocol.

#### Se connecter à un Realm

Pour rejoindre un Realm auquel votre compte Minecraft a été invité, vous pouvez passer un objet `realms` avec une fonction de sélection comme ci-dessous.

```js
const client = mineflayer.createBot({
  username: 'email@example.com', // nom d'utilisateur minecraft
  realms: {
    // Cette fonction est appelée avec un tableau de Realms que le compte peut rejoindre. Elle doit retourner celui qu'elle veut rejoindre.
    pickRealm: (realms) => realms[0]
  },
  auth: 'microsoft'
})
```

### Voir ce que fait votre bot

Grâce au projet [prismarine-viewer](https://github.com/PrismarineJS/prismarine-viewer), il est possible d'afficher dans une fenêtre de navigateur ce que fait votre bot.
Il suffit d'exécuter `npm install prismarine-viewer` et d'ajouter ceci à votre bot :
```js
const { mineflayer: mineflayerViewer } = require('prismarine-viewer')
bot.once('spawn', () => {
  mineflayerViewer(bot, { port: 3007, firstPerson: true }) // port est le port du serveur minecraft, si firstPerson est false, vous obtenez une vue à vol d'oiseau
})
```
Et vous obtiendrez une vue *en direct* ressemblant à ceci :

[<img src="https://prismarinejs.github.io/prismarine-viewer/test_1.16.1.png" alt="viewer" width="500">](https://prismarinejs.github.io/prismarine-viewer/)

#### Plus d'exemples

| exemple | description |
|---|---|
|[viewer](https://github.com/PrismarineJS/mineflayer/tree/master/examples/viewer) | Afficher la vue du monde de votre bot dans le navigateur |
|[pathfinder](https://github.com/PrismarineJS/mineflayer/tree/master/examples/pathfinder) | Faire en sorte que votre bot aille à n'importe quel endroit automatiquement |
|[chest](https://github.com/PrismarineJS/mineflayer/blob/master/examples/chest.js) | Utiliser les coffres, fours, distributeurs, tables d'enchantement |
|[digger](https://github.com/PrismarineJS/mineflayer/blob/master/examples/digger.js) | Apprendre comment créer un bot simple capable de creuser des blocs |
|[discord](https://github.com/PrismarineJS/mineflayer/blob/master/examples/discord.js) | Connecter un bot discord avec un bot mineflayer |
|[jumper](https://github.com/PrismarineJS/mineflayer/blob/master/examples/jumper.js) | Apprendre comment se déplacer, sauter, conduire des véhicules, attaquer des entités proches |
|[ansi](https://github.com/PrismarineJS/mineflayer/blob/master/examples/ansi.js) | Afficher le chat de votre bot avec toutes les couleurs du chat affichées dans votre terminal |
|[guard](https://github.com/PrismarineJS/mineflayer/blob/master/examples/guard.js) | Faire en sorte qu'un bot garde une zone définie contre les mobs proches |
|[multiple-from-file](https://github.com/PrismarineJS/mineflayer/blob/master/examples/multiple_from_file.js) | Ajouter un fichier texte avec des comptes et les faire tous se connecter |

Et bien d'autres dans le dossier [examples](https://github.com/PrismarineJS/mineflayer/tree/master/examples).

### Modules

Beaucoup de développement actif se fait dans de petits packages npm qui sont utilisés par mineflayer.

#### The Node Way&trade;

> "When applications are done well, they are just the really application-specific, brackish residue that can't be so easily abstracted away. All the nice, reusable components sublimate away onto github and npm where everybody can collaborate to advance the commons." — substack from ["how I write modules"](https://gist.github.com/substack/5075355)

#### Modules

Voici les principaux modules qui constituent mineflayer :

| module | description |
|---|---|
| [minecraft-protocol](https://github.com/PrismarineJS/node-minecraft-protocol) | Analyse et sérialise les paquets minecraft, plus l'authentification et le chiffrement.
| [minecraft-data](https://github.com/PrismarineJS/minecraft-data) | Module indépendant du langage fournissant des données minecraft pour les clients, serveurs et bibliothèques minecraft.
| [prismarine-physics](https://github.com/PrismarineJS/prismarine-physics) | Fournit le moteur de physique pour les entités minecraft
| [prismarine-chunk](https://github.com/PrismarineJS/prismarine-chunk) | Une classe pour contenir les données de chunk pour Minecraft
| [node-vec3](https://github.com/PrismarineJS/node-vec3) | Mathématiques vectorielles 3D avec des tests unitaires robustes
| [prismarine-block](https://github.com/PrismarineJS/prismarine-block) | Représente un bloc minecraft avec ses données associées
| [prismarine-chat](https://github.com/PrismarineJS/prismarine-chat) | Un analyseur pour un message de chat minecraft (extrait de mineflayer)
| [node-yggdrasil](https://github.com/PrismarineJS/node-yggdrasil) | Bibliothèque Node.js pour interagir avec le système d'authentification de Mojang, connu sous le nom d'Yggdrasil
| [prismarine-world](https://github.com/PrismarineJS/prismarine-world) | L'implémentation principale des mondes pour prismarine
| [prismarine-windows](https://github.com/PrismarineJS/prismarine-windows) | Représente les fenêtres minecraft
| [prismarine-item](https://github.com/PrismarineJS/prismarine-item) | Représente un objet minecraft avec ses données associées
| [prismarine-nbt](https://github.com/PrismarineJS/prismarine-nbt) | Un analyseur NBT pour node-minecraft-protocol
| [prismarine-recipe](https://github.com/PrismarineJS/prismarine-recipe) | Représente les recettes minecraft
| [prismarine-biome](https://github.com/PrismarineJS/prismarine-biome) | Représente un biome minecraft avec ses données associées
| [prismarine-entity](https://github.com/PrismarineJS/prismarine-entity) | Représente une entité minecraft


### Debug

Vous pouvez activer le debug du protocole en utilisant `DEBUG` comme variable d'environnement:

```bash
DEBUG="minecraft-protocol" node [...]
```

Sur windows :
```
set DEBUG=minecraft-protocol
node your_script.js
```

## Plugins tiers

Mineflayer est extensible ; n'importe qui peut créer un plugin qui ajoute une API de plus haut niveau au-dessus de Mineflayer.

Les plus récents et utiles sont :

 * [minecraft-mcp-server](https://github.com/yuniko-software/minecraft-mcp-server) Un serveur MCP pour mineflayer, permettant d'utiliser mineflayer depuis un LLM
 * [pathfinder](https://github.com/Karang/mineflayer-pathfinder) - recherche de chemin A* avancée avec de nombreuses fonctionnalités configurables
 * [prismarine-viewer](https://github.com/PrismarineJS/prismarine-viewer) - visionneuse de chunks web simple
 * [web-inventory](https://github.com/ImHarvol/mineflayer-web-inventory) - visionneuse d'inventaire basée sur le web
 * [statemachine](https://github.com/PrismarineJS/mineflayer-statemachine) - Une API de machine à états pour des comportements de bot plus complexes
 * [Armor Manager](https://github.com/G07cha/MineflayerArmorManager) - gestion automatique de l'armure
 * [Dashboard](https://github.com/wvffle/mineflayer-dashboard) - Tableau de bord frontend pour bot mineflayer
 * [PVP](https://github.com/PrismarineJS/mineflayer-pvp) - API facile pour PVP et PVE de base.
 * [Auto Eat](https://github.com/link-discord/mineflayer-auto-eat) - Alimentation automatique.
 * [Auto Crystal](https://github.com/link-discord/mineflayer-autocrystal) - Placement et destruction automatiques de cristaux de l'End.
 * [Tool](https://github.com/TheDudeFromCI/mineflayer-tool) - Un utilitaire pour la sélection automatique d'outil/arme avec une API de haut niveau.
 * [Hawkeye](https://github.com/sefirosweb/minecraftHawkEye) - Un utilitaire pour utiliser la visée automatique avec des arcs.
 * [GUI](https://github.com/firejoust/mineflayer-GUI) - Interagir avec les fenêtres GUI imbriquées en utilisant async/await
 * [Projectile](https://github.com/firejoust/mineflayer-projectile) - Obtenir l'angle de lancement requis pour les projectiles
 * [Movement](https://github.com/firejoust/mineflayer-movement) - Mouvement du joueur fluide et réaliste, mieux adapté au PvP
 * [Collect Block](https://github.com/PrismarineJS/mineflayer-collectblock) - API rapide et simple de collecte de blocs.

 Mais consultez également :

 * [radar](https://github.com/andrewrk/mineflayer-radar/) - interface radar web
   utilisant canvas et socket.io. [Démo YouTube](https://www.youtube.com/watch?v=FjDmAfcVulQ)
 * [auto-auth](https://github.com/G07cha/MineflayerAutoAuth) - authentification de bot basée sur le chat
 * [Bloodhound](https://github.com/Nixes/mineflayer-bloodhound) - déterminer qui et quoi est responsable des dommages à une autre entité
 * [tps](https://github.com/SiebeDW/mineflayer-tps) - obtenir le tps actuel (tps traité)
 * [panorama](https://github.com/IceTank/mineflayer-panorama) - prendre des images panoramiques de votre monde
 * [player-death-event](https://github.com/tuanzisama/mineflayer-death-event) - émettre un événement de mort de joueur dans Mineflayer.

## Projets utilisant Mineflayer

 * [Voyager](https://github.com/MineDojo/Voyager) Un agent incarné ouvert avec de grands modèles de langage
 * [mindcraft](https://github.com/kolbytn/mindcraft) Bibliothèque pour utiliser mineflayer avec des LLM
 * [rom1504/rbot](https://github.com/rom1504/rbot)
   - [YouTube - construire un escalier en colimaçon](https://www.youtube.com/watch?v=UM1ZV5200S0)
   - [YouTube - répliquer un bâtiment](https://www.youtube.com/watch?v=0cQxg9uDnzA)
 * [Darthfett/Helperbot](https://github.com/Darthfett/Helperbot)
 * [vogonistic/voxel](https://github.com/vogonistic/mineflayer-voxel) - visualiser ce que
   fait le bot en utilisant voxel.js
 * [JonnyD/Skynet](https://github.com/JonnyD/Skynet) -  enregistrer l'activité des joueurs sur une API en ligne
 * [MinecraftChat](https://github.com/rom1504/MinecraftChat) (dernière version open source, créée par AlexKvazos) -  Client de chat Minecraft basé sur le web
 * [Cheese Bot](https://github.com/Minecheesecraft/Cheese-Bot) - Bot basé sur les plugins avec une interface graphique propre. Créé avec Node-Webkit.
 * [Chaoscraft](https://github.com/schematical/chaoscraft) - Bot Minecraft utilisant des algorithmes génétiques, voir [ses vidéos youtube](https://www.youtube.com/playlist?list=PLLkpLgU9B5xJ7Qy4kOyBJl5J6zsDIMceH)
 * [hexatester/minetelegram](https://github.com/hexatester/minetelegram) -  Pont Minecraft - Telegram, construit sur mineflayer & telegraf.
 * [PrismarineJS/mineflayer-builder](https://github.com/PrismarineJS/mineflayer-builder) - Imprime des schémas minecraft en survie, en conservant l'orientation
 * [SilkePilon/OpenDeliveryBot](https://github.com/SilkePilon/OpenDeliveryBot) - Bot Minecraft en python pour livrer des objets d'un endroit à un autre.
 * [et des centaines d'autres](https://github.com/PrismarineJS/mineflayer/network/dependents) - Tous les projets que github a détecté comme utilisant mineflayer


## Tests

### Tester tout

Exécutez simplement :

```bash
npm test
```

### Tester une version spécifique
Exécutez

```bash
npm run mocha_test -- -g <version>
```

où `<version>` est une version minecraft comme `1.12`, `1.15.2`...

### Tester un test spécifique
Exécutez

```bash
npm run mocha_test -- -g <test_name>
```

où `<test_name>` est un nom de test comme `bed`, `useChests`, `rayTrace`...

### Exemple

```bash
npm run mocha_test -- -g "1.18.1.*BlockFinder"
```
pour exécuter le test block finder pour 1.18.1

## Licence

[MIT](/LICENSE)
