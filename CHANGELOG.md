<!-- SPDX-License-Identifier: MIT -->
# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

## [0.1.6] - 2020-03-12

### Added

* Add the ability to redact player ip addresses and coords
  * Banning a player by ip will still work, just not display in the logs.
  * Further customization should come later

### Fixed

* Fixed players getting kicked due to improper change for World.random
  * This was only in the dev builds but still was given out to some users

### Removed

* Networking System based on Velocity and Yatopia
  * This unfortunately touched a few areas that a version agnostic packet manipulation framework was using.
* Shapeless crafting from Airplane backport
  * This was only in dev builds and was a bad, broken port

## [0.1.5] - 2020-03-07

### Added

* Fair natural spawning
  * Searches around the players to avoid their locations for spawning in monsters if they are hitting the limit.
* Load Chunks for login asyncronously
* Removed EnumSet allocations in crafting checks
* Lighting system optimizations
  * currently around lambda allocations being removed, need to work on the algorithm and making it more async
* Added a dionysus commands reload and version

### Changed

* Change logging levels in PlayerConnection on spammy messages

## [0.1.4] - 2020-02-13

### Added

* Velocity Native compression/crypto from Tuinity!
* NBT Compression Levels (Chunks use NBT)
* New Networking System based on Yatopia and Velocity

### Changed

* Paperclip was updated to the latest version

## [0.1.3] - 2020-02-10

### Fixed

* Dispenser Shulker Box Crash

## [0.1.2] - 2020-02-10

### Removed

* AntiPhysics crash
  * this was half baked and not fully tested, needs more work.

## [0.1.0] - 2020-02-09

### New Features 

* TileEntity Limit Optimization
* AntiBook crash implementation
* AntiPhysics crash implementation
* CompactSineLUT
  * taken from Lithium by CaffeineMC/Jellysquid
* Switched out Math.sin and Math.cos implementations for MathHelper versions
* Switched non-seeded random to use XorShift Random class
* Limit AI Checks
    * Credit to: John200410

### Backports

Credit goes to Paper or Tuinity unless specified in the patch.

* Faster redstone torch rapid clock removal!
* Optimize redstone algorithm aka Eigencraft redstone algorithm
* Optimize Network Manager
* Buffer joins to world
* ItemInHand crash
* Cache EnumDirection adjacent positions
* Optimize time updates
* Reduce memory footprint of NBTTagCompound
* Avoid containsKey -> get() pattern for getTileEntity
* waitForAsyncTasksShutdown on shutdown
* cap per-thread NIO cache size when not specified by the server owner

### Removed Paper or Vanilla Features

* Anti-Xray
* LegacyPingHandler

### Fixed Vanilla Bugs

* MC-47080 - Spectators count as "players" for purposes of sleeping in SMP
