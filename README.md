# NoMoreQuests

A custom Vencord userplugin that removes Discord Quest promotions, Quest buttons, Quest cards, and Quest popups from the client UI.

It is meant for people who do not want Discord's Quest ads taking up space in the app.

## What It Does

- Hides the Quests tab and Quest navigation links.
- Removes Quest promo cards from the main Discord UI.
- Detects newer promoted Quest cards that use labels like:
  - `Promoted`
  - `Watch 3m`
  - `Get Reward!`
  - `Quest`
  - `Orbs`
- Hides the full promo card container instead of only hiding inner text or images.
- Watches for new Quest cards that Discord renders after startup.

## What It Does Not Do

- It does not auto-complete Quests.
- It does not spoof game, stream, or video progress.
- It does not claim rewards.
- It does not modify your account or Quest state.

This plugin only hides Quest-related UI from your local Discord client.

## Installing Vencord From Source

Custom Vencord plugins require a source build of Vencord. The normal one-click installer is not enough for custom userplugins.

1. Install the prerequisites:
   - [Git](https://git-scm.com/downloads)
   - [Node.js](https://nodejs.org/)
   - [pnpm](https://pnpm.io/installation)

2. Verify they are available in your terminal:

```sh
git --version
node --version
pnpm --version
```

3. Clone Vencord:

```sh
git clone https://github.com/Vendicated/Vencord
cd Vencord
```

4. Install Vencord dependencies:

```sh
pnpm install --frozen-lockfile
```

## Installing This Plugin

From inside your Vencord folder:

```sh
mkdir -p src/userplugins
cd src/userplugins
git clone https://github.com/jordanw0204-rgb/noMoreQuests
```

Then build and inject Vencord:

```sh
cd ../..
pnpm build
pnpm inject
```

After injection finishes, fully restart Discord.

## Enabling The Plugin

1. Open Discord.
2. Go to `User Settings`.
3. Open the `Vencord` plugin settings.
4. Enable `NoMoreQuests`.
5. Restart Discord if Quest cards were already visible.

## Updating

From the plugin folder:

```sh
cd src/userplugins/noMoreQuests
git pull
```

Then rebuild and reinject Vencord:

```sh
cd ../../..
pnpm build
pnpm inject
```

Restart Discord afterward.

## Troubleshooting

- If the plugin does not appear, confirm the folder is exactly `src/userplugins/noMoreQuests`.
- If a Quest card still appears, Discord may have changed the card text or layout. Open an issue with a screenshot and the visible text on the card.
- If an empty blank card appears, the selector may be hiding inner content instead of the full container. Update the plugin and rebuild.
- If Vencord fails to build, run `pnpm install --frozen-lockfile` from the Vencord folder and try again.

## Notes

This is a custom userplugin, not an official Vencord plugin. Use it at your own risk and read the source before installing custom plugins from anyone.

Official Vencord docs:

- [Installing Vencord from source](https://docs.vencord.dev/installing/)
- [Installing custom plugins](https://docs.vencord.dev/installing/custom-plugins/)
