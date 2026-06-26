# Vencord No More Quests

No More Quests hides Discord Quest promotions in the desktop client.

It targets the Quest tab, Quest navigation links, and the promo cards Discord drops into the app, including newer cards that show text like `Promoted`, `Watch 3m`, or `Get Reward!`.

## Features

- Hides Quest navigation links.
- Removes Quest promo cards from the main UI.
- Watches for Quest cards that render after startup.
- Hides the full promo card container instead of leaving an empty shell behind.

## Requirements

- A source build of Vencord.
- Discord desktop.

## Install Vencord From Source

Custom Vencord plugins only work with a source build.

Install:

- [Git](https://git-scm.com/downloads)
- [Node.js](https://nodejs.org/)
- [pnpm](https://pnpm.io/installation)

Then clone and install Vencord:

```sh
git clone https://github.com/Vendicated/Vencord
cd Vencord
pnpm install --frozen-lockfile
```

## Install This Plugin

From the Vencord folder:

```sh
mkdir -p src/userplugins
cd src/userplugins
git clone https://github.com/jordanw0204-rgb/vencord-no-more-quests noMoreQuests
```

Build and inject Vencord:

```sh
cd ../..
pnpm build
pnpm inject
```

Restart Discord after injection.

## Enable

1. Open Discord settings.
2. Go to `Vencord` -> `Plugins`.
3. Enable `NoMoreQuests`.
4. Restart Discord if Quest cards were already visible.

## Update

```sh
cd src/userplugins/noMoreQuests
git pull
cd ../../..
pnpm build
pnpm inject
```

Restart Discord after updating.

## Troubleshooting

- Plugin missing: make sure the folder is `src/userplugins/noMoreQuests`.
- Quest card still appears: Discord likely changed the card copy or layout. Open an issue with a screenshot.
- Blank card remains: update the plugin, rebuild Vencord, and restart Discord.
- Build failed: run `pnpm install --frozen-lockfile` in the Vencord folder.

## Links

- [Vencord source install docs](https://docs.vencord.dev/installing/)
- [Vencord custom plugin docs](https://docs.vencord.dev/installing/custom-plugins/)
