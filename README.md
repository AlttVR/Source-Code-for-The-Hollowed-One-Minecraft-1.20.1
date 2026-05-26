# Hollow Stalker Horror Mod

This workspace includes Forge, NeoForge, Fabric, and Quilt 1.20.1 low-code/data-driven jars plus the original data pack version. The mod is authored as `Render4` and adds a hostile stalker with command-driven behavior:

- stalks the nearest survival/adventure player
- spawns about 300 blocks away and approaches on foot
- includes four stalker variants with separate textures and behavior
- breaks blocks around itself while pursuing
- instantly kills chased players it catches
- plays strange, off ambience and warning noises
- triggers a scare event every 2-5 minutes
- has easy, normal, and nightmare presets
- starts with a grace period before Hollow sprints
- plays rare fake countdown events when Hollow is not nearby
- can kick a survival player with an eerie message during one event
- prevents block placement during the chase by putting chased survival players into adventure mode

## Forge 1.20.1 Install

1. Copy `hollow_stalker-1.3.0-forge-1.20.1.jar` into your Minecraft `mods` folder.
2. Launch Minecraft Java with Forge 1.20.1.
3. Open a world and run `/function hollow:summon` to start the chase.

The stalker uses the included eyeless humanoid texture. In this low-code Forge version, that texture is applied by replacing the vanilla husk texture while the mod is loaded.

When the chase starts, survival players near the stalker are switched into adventure mode so blocks cannot be placed to escape. The mod keeps a tiny invisible chase anchor loaded so the 300-block spawn can keep moving; `/function hollow:remove` restores chased players to survival mode and clears that anchor.

Hollow also restores chased players if they move too far from the chase or after Hollow catches them, so they should not stay stuck in adventure mode in singleplayer or multiplayer.

## Data Pack Install

1. Copy the `NightmareStalker` folder into your world's `datapacks` folder.
2. Open the world and run `/reload`.
3. Run `/function nightmare:summon_stalker` to spawn it near you.

If Minecraft marks the pack as made for a different version, the commands may still work. If it refuses to load, open `NightmareStalker/pack.mcmeta` and change `pack_format` to the number your Minecraft version expects.

## Commands

- `/function hollow:summon` - start the chase.
- `/function hollow:start` - start the chase.
- `/function hollow:summon_eyeless` - summon the classic eyeless Steve hunter.
- `/function hollow:summon_unknown` - summon the faster pressure hunter.
- `/function hollow:summon_mimic` - summon the behind-you variant.
- `/function hollow:summon_longmouth` - summon the block-breaking heavy variant.
- `/function hollow:summon_all` - summon all variants.
- `/function hollow:easy` - slower chase, longer grace period, rarer fake events.
- `/function hollow:normal` - default chase.
- `/function hollow:nightmare` - faster chase, shorter grace period, more fake events.
- `/function hollow:remove` - remove Hollow and restore chased players.
- `/function hollow:stop` - remove Hollow and restore chased players.
- `/function hollow:restore` - restore chased players if a multiplayer session needs cleanup.
- `/function hollow:reset` - remove Hollow and reload its scoreboards.
- `/function hollow:load` - reset scoreboards after manual edits.
- `/function hollow:help` - show the commands in-game.

## Warning

The Stalker breaks blocks with `destroy`, so it can damage builds. Use it in a copy of your world if you care about the terrain or structures.
