<div align="center">

<img src="https://mercysf.app/icon.png" alt="" width="120">

# Mercy SF

### A free Shakes & Fidget bot for Windows, macOS and Linux

[![Website](https://img.shields.io/badge/Website-mercysf.app-e01020?style=for-the-badge&labelColor=0a0708)](https://mercysf.app/)
[![Download](https://img.shields.io/badge/Download-Windows%20·%20macOS%20·%20Linux-e01020?style=for-the-badge&labelColor=0a0708)](https://mercysf.app/downloads)
[![Docs](https://img.shields.io/badge/Docs-10%20languages-e01020?style=for-the-badge&labelColor=0a0708)](https://mercysf.app/docs/)

![Version](https://img.shields.io/badge/version-2.17.4-0a0708?style=flat-square)
![Price](https://img.shields.io/badge/price-free,%20no%20tiers-0a0708?style=flat-square)
![Modules](https://img.shields.io/badge/modules-26-0a0708?style=flat-square)
![Built with](https://img.shields.io/badge/built%20with-Rust%20%2B%20Tauri%202-0a0708?style=flat-square)

[![Mercy SF](https://mercysf.app/og-image.png)](https://mercysf.app/)

**[mercysf.app](https://mercysf.app/)** &nbsp;·&nbsp; [Download](https://mercysf.app/downloads) &nbsp;·&nbsp; [Documentation](https://mercysf.app/docs/) &nbsp;·&nbsp; [Changelog](https://mercysf.app/changelog) &nbsp;·&nbsp; [Discord](https://discord.gg/m8MCJtDgXc)

</div>

---

**Mercy SF** plays the idle RPG *Shakes & Fidget* for you. Quests, arena, dungeons, fortress, underworld, pets, guild, the daily tavern rounds and the big timed events, all of it running on its own while you do something else.

It is a standalone desktop application, not a game mod. It signs in through the official single sign-on and drives your account through the game's own interface, sending the same requests your browser sends. Nothing is injected and nothing is patched.

**Everything is free.** Every module is unlocked for everyone. There is no licence key, no supporter tier that gets the good features, and no trial.

> This repository is the public home of the project and exists to point you at the website. The application itself is distributed from **[mercysf.app/downloads](https://mercysf.app/downloads)**.

## Download

### [mercysf.app/downloads](https://mercysf.app/downloads)

| Platform | Format |
| --- | --- |
| **Windows** | `.exe` installer or `.msi` |
| **macOS** | `.dmg` for Apple Silicon and Intel |
| **Linux** | `.AppImage` and `.deb` |
| **Headless** | CLI binaries for Windows, macOS and Linux, including ARM64 for a Raspberry Pi |

No account is needed to download. The desktop app keeps itself up to date, every build is signed, and the updater verifies the signature before installing. Your accounts and settings survive an update.

## What it automates

Twenty-six modules, each with a page in the documentation explaining what it decides and why.

### The daily loop

| Module | What it does |
| --- | --- |
| **Quests, tavern, expeditions** | Ranks the three quests on offer by reward per second rather than by raw reward, handles beer and the thirst for adventure, and prefers an expedition where the server has them |
| **Dungeons, Twister and Tower** | Simulates the current enemy of every open dungeon and fights the one it is most likely to win, so a free fight is never spent on a loss |
| **Fortress** | Gathers wood, stone and silver, searches the gem mine, queues building upgrades, and runs attacks when you allow them |
| **Underworld** | Collects souls and silver, upgrades buildings, and respects your build caps |
| **Pets** | Feeding, pet dungeons, pet arena and habitat exploration |
| **Daily rewards** | Calendar, wheel of fortune, dice game, toilet and the mount, plus coupon codes |

### Fighting, with a reason

| Module | What it does |
| --- | --- |
| **Arena** | Scores every candidate on missing scrapbook items, daily experience and rank, multiplies by the simulated win chance, and names the opponent it will fight next and why |
| **Scrapbook hunting** | Crawls the Hall of Fame in the background and attacks the beatable player carrying the most items your album is still missing, across the whole server rather than the three the arena suggests |
| **Battle simulator** | Turns "should I attack this player" into a number, with a full round by round replay of any fight |
| **Hall of Fame** | Search and a player pool the hunt draws from |

### The timed events

This is the part most bots leave out, and the part that costs the most clicks to play by hand.

| Event | What it does |
| --- | --- |
| **World Boss** | Keeps the catapult loaded, re-aims at the weak point, buys upgrades and collects the chests. It never pays in mushrooms, and it stops buying permanently for an account if it ever sees one move |
| **Hellevator** | Climbs on key cards and buys a treat from Beelzebub's Emporium once a fight is actually lost, because a treat lasts two floors and one bought at the bottom helps where no help was needed |
| **Legendary Dungeon** | Doors, encounters, blessings and curses, with three separate ceilings on what reviving may cost |
| **Event detection** | Works out which event is genuinely running instead of firing at one that closed on Sunday, which is harder than it sounds because the server keeps sending the data afterwards |

### Economy, guild and control

| Module | What it does |
| --- | --- |
| **Blacksmith, witch, enchanting** | Dismantles, upgrades and enchants, and keeps back the metal and arcane that pulling a gem out of an item costs, so a gem is never destroyed with the item it sits in |
| **Inventory and shops** | Auto-equips what is better, sells or dismantles the rest, with an exception list for everything you never want sold |
| **Gems** | Class aware and socket aware. Empty sockets are filled first, and a good gem is never overwritten by a mediocre one |
| **Guild** | Portal, hydra, raids, and readying up for attack and defence at a time you choose |
| **Server start** | Plays the opening of a fresh server in phases, because the first week is decided by order and consistency rather than by effort |
| **Achievements** | An opt-in engine that will take a detour for an achievement, off by default |
| **Analytics and logs** | What it did, why it skipped what it skipped, and whether last week's change actually helped |
| **Many characters at once** | Every account in one window, each with its own settings, schedule and log |
| **Headless CLI** | A console build with a documented JSON interface, for a VPS or your own dashboard |

Full guides: **[mercysf.app/docs](https://mercysf.app/docs/)**

## Mushrooms are real money, so nothing spends them by default

Every single feature that can spend a mushroom is a separate switch, and every one of them ships off. On top of those there are two limits that protect different things:

| Setting | Protects |
| --- | --- |
| `min_mushrooms` | **The balance.** Nothing spends below this floor |
| `mushroom_budget_*` | **The rate.** Use at most twenty a week, for example |

You want both. An account that earns mushrooms steadily can sit above its floor forever while spending everything it earns, and a floor alone cannot see that.

## It tells you what it is doing

A bot that says "waiting" is very hard to trust. Mercy SF names the opponent it will fight next and the reason it picked them, shows the score each candidate got, and when it does nothing it says why in one sentence.

There is also an **anonymous mode**: one switch in the header hides every name in the app, your characters, your accounts, opponents, guilds and the logs, so a screenshot can be shared as it is. Names are replaced by a stable stand-in rather than blanked, so you can still tell whether the player who beat you twice was the same player.

## Ten languages

The app, the website and all thirty documentation pages are available in:

English &nbsp;·&nbsp; [Deutsch](https://mercysf.app/docs/de/) &nbsp;·&nbsp; [Français](https://mercysf.app/docs/fr/) &nbsp;·&nbsp; [Español](https://mercysf.app/docs/es/) &nbsp;·&nbsp; [Italiano](https://mercysf.app/docs/it/) &nbsp;·&nbsp; [Polski](https://mercysf.app/docs/pl/) &nbsp;·&nbsp; [Čeština](https://mercysf.app/docs/cs/) &nbsp;·&nbsp; [Русский](https://mercysf.app/docs/ru/) &nbsp;·&nbsp; [日本語](https://mercysf.app/docs/ja/) &nbsp;·&nbsp; [中文](https://mercysf.app/docs/zh/)

Release notes are written in all ten before a version ships, not translated afterwards.

## What it costs to run

Built with Rust and Tauri 2, using the operating system's own WebView. There is no bundled Chromium and no Node runtime in the background. About 200 MB of memory per running character.

## Is it safe?

Two separate questions, and they deserve separate answers.

**Is the software safe?** It runs entirely on your machine. Nothing about how you play is collected, sold or sent anywhere. There is no telemetry, no advertising and nothing bundled in the installer. Your credentials are stored locally and encrypted, and there is no account server holding them.

**Is automating an account safe?** That is a different question, and the honest answer is that automation can be against the game's terms of service. The consequence of a breach, whether a warning, a suspension or the loss of a character built over years, falls on you and on nobody else. Read the game's own terms and decide for yourself.

That risk is why Mercy SF is deliberately conservative about how fast it acts, and why the crawler has a per-minute rate limit rather than only a per-cycle one.

## Links

| | |
| --- | --- |
| Website | https://mercysf.app |
| Download | https://mercysf.app/downloads |
| Documentation | https://mercysf.app/docs/ |
| Changelog | https://mercysf.app/changelog |
| Roadmap | https://mercysf.app/roadmap |
| Support | https://mercysf.app/support |
| Discord | https://discord.gg/m8MCJtDgXc |
| Ko-fi | https://ko-fi.com/senseiissei |

## FAQ

**What is Mercy SF?**
A program that plays *Shakes & Fidget* for you: the repetitive daily tasks run on their own, so your character keeps progressing without you clicking through every menu.

**Is it a Shakes and Fidget mod?**
No. It is a standalone application that talks to the same official servers your browser talks to, sending the same requests the game itself sends. Nothing is injected into the game client and nothing is patched.

**Does it cost anything?**
No. Every module is unlocked for everyone, with no licence key, no supporter tier and no trial.

**Which platforms?**
Windows, macOS on both Apple Silicon and Intel, and Linux, plus a headless CLI build that also runs on ARM64 boards.

**Can it run several accounts?**
Yes. Each character keeps its own settings, schedule and log, and one overview screen shows all of them.

**Will it spend my mushrooms?**
Not unless you switch that on. Every mushroom spender is a separate setting and all of them ship off, with a reserve and a budget on top.

---

<div align="center">

**[mercysf.app](https://mercysf.app/)**

<sub>Mercy SF is an independent tool and is not affiliated with, endorsed by, or connected to Playa Games GmbH or Shakes & Fidget. All trademarks belong to their owners. Use at your own risk.</sub>

</div>
