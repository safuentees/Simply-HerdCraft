# Simply HerdCraft

Simply HerdCraft is an optimization modpack for **26w14a**, the April Fools snapshot for the never-released [HerdCraft Update](https://www.minecraft.net/en-us/article/the-herdcraft-update).

## What is 26w14a?

26w14a is the 2026 April Fools snapshot that completely overhauls Minecraft's inventory system. Instead of storing items, every block and item becomes a **Living Block** entity that follows your commands. You can ask them to follow you, place themselves in crafting grids, or even fight enemies on your behalf.

## Mod List

Every mod in this pack has been handpicked and tested to be compatible with 26w14a, including two custom-built mods:

- **Sodium 0.8.9-SNAPSHOT** — Dev build from [CaffeineMC](https://github.com/CaffeineMC/sodium) with FRAPI support for 26.1+
- **Lithium 0.23.0-patched** — Custom build with `ItemEntity` references removed (ItemEntity was deleted in 26w14a)

For the full mod list, see the [Modrinth page](https://modrinth.com/modpack/simply-herdcraft) (if published).

### Performance Mods
Sodium, Lithium (patched), ImmediatelyFast, FerriteCore, Entity Culling, MoreCulling, Dynamic FPS

### Visual Enhancement Mods
Entity Model Features, Entity Texture Features, LambDynamicLights, Skyboxify, Cape Provider, Puzzle

### Utility Mods
Mod Menu, Fabric API, YACL, Cloth Config, Language Reload, Borderless Mining, Crash Assistant, No Chat Reports, More Chat History, Remove Reloading Screen, and more

## Custom Builds

Two mods required source modifications to work with 26w14a:

### Lithium (patched)
26w14a removed the `ItemEntity` class entirely (items are now Living Blocks). Lithium's source was patched to:
- Remove all `ItemEntity` class references from core tracking code
- Delete the `FrogAttackablesSensorMixin` (targets a renamed method)
- Delete hopper item-collection mixins (hoppers can't collect Living Blocks)
- Delete raid banner pickup optimization
- Relax Minecraft version constraint to `*`

~95% of Lithium's optimizations remain active (chunks, world, blocks, collisions, pathfinding, math, explosions, spawning).

### Sodium (dev build)
Sodium 0.8.7 crashes on 26.1+ with Fabric API due to missing FRAPI (Fabric Rendering API) implementation for new `BlockFeatureRenderer` code. The 0.8.9-SNAPSHOT dev build from CaffeineMC's CI includes the FRAPI fix.

## Installation

1. Download the `.mrpack` from [Releases](../../releases)
2. Import into **Modrinth App**, **Prism Launcher**, or **ATLauncher**
3. Requires **Java 25** and **Fabric Loader 0.18.6**

## Credits

- Custom Sodium and Lithium builds sourced from [CaffeineMC](https://github.com/CaffeineMC)
