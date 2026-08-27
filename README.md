MineviaAC — README

Overview

MineviaAC is a lightweight custom anticheat designed for Minevia’s Minecraft PvP environment.

The main goal is to detect suspicious behaviour without instantly punishing players or creating unnecessary false flags.

MineviaAC uses a Violation Level system (VL). Players gain VL when checks detect suspicious behaviour. Staff can review players before taking action.

Main Features

* Blue §9[Minevia] anticheat prefix
* Anticheat alerts visible only to OPs by default
* 100 VL staff review system
* Clickable KICK and NO KICK options
* No automatic bans
* Violation levels decrease over time
* Player flag history
* Staff verbose mode
* Player inspection commands
* VL reset command
* Temporary exemptions
* Console logging
* Ping compensation
* TPS compensation
* Teleport grace period
* Respawn grace period
* Velocity grace period
* Explosion grace period
* Potion effect handling
* Water handling
* Ladder handling
* Web handling
* Slime handling
* Vehicle exemptions
* BedWars movement exemptions
* Different VL amounts depending on check confidence

Alert Example

[Minevia] Chillkb flagged KillAura A (VL: 34/100)

Only authorized staff will receive these alerts.

100 VL Review

When a player reaches 100 VL, MineviaAC does not automatically ban them.

Staff receive:

[Minevia] Chillkb reached 100 VL
[KICK] [NO KICK]

KICK

Kicks the player for anticheat flagging.

Example kick message:

Minevia
You were kicked for suspicious gameplay.
Please contact staff if you believe this was a mistake.

NO KICK

Dismisses the current punishment recommendation and allows staff to continue monitoring the player.

Combat Checks

MineviaAC can include checks for:

* KillAura A
* KillAura B
* KillAura C
* MultiAura
* Reach
* Hitbox
* AimAssist
* Snap rotations
* Impossible rotations
* Invalid pitch
* AutoClicker
* CPS anomalies
* Criticals
* Impossible attack distance
* Impossible attack timing
* Inventory attacks
* Suspicious target switching
* Attacking through blocks
* FastBow-style behaviour

Movement Checks

* Fly A
* Fly B
* Speed A
* Speed B
* Step
* HighJump
* LongJump
* NoFall
* Jesus
* Phase
* Ground spoof
* Abnormal horizontal movement
* Abnormal vertical movement
* Air movement
* Sprint anomalies
* Sneak anomalies
* InventoryMove
* Timer
* Abnormal movement packet frequency

Knockback Checks

* AntiKB Horizontal
* AntiKB Vertical
* Zero velocity
* Velocity manipulation
* Impossible post-knockback movement
* Repeated ignored velocity

These checks should use multiple samples before heavily increasing VL to reduce false positives.

World Checks

* Scaffold A
* Scaffold B
* Scaffold C
* Scaffold Rotation
* FastPlace
* FastBreak
* Nuker
* Impossible block reach
* Impossible placement reach
* Suspicious movement/place synchronization

Packet Checks

* BadPackets A
* BadPackets B
* BadPackets C
* Invalid movement values
* Impossible coordinates
* NaN/infinite position protection
* Invalid pitch
* Impossible packet ordering
* Excessive movement packets
* Excessive action packets

Staff Commands

/mineviaac

Shows MineviaAC information.

/mineviaac alerts

Enables or disables anticheat alerts for yourself.

/mineviaac info <player>

Shows:

* Current VL
* Ping
* Recent flags
* Highest flag
* Total flags

/mineviaac verbose <player>

Shows more detailed detection information for a specific player.

/mineviaac reset <player>

Resets the player’s violation level.

/mineviaac exempt <player>

Temporarily exempts a player from checks.

/mineviaac reload

Reloads the plugin configuration.

Permissions

mineviaac.alerts
mineviaac.info
mineviaac.verbose
mineviaac.reset
mineviaac.exempt
mineviaac.reload
mineviaac.kick

OPs receive all MineviaAC permissions by default.

Violation System

Different checks should add different amounts of VL.

Example:

Minor suspicious behaviour: +1 to +3 VL
Moderate detection: +4 to +8 VL
Strong detection: +10 to +20 VL
Extremely confident detection: +20+ VL

A single unusual packet or movement should normally not cause a punishment.

MineviaAC should look for repeated or highly confident behaviour.

False Positive Protection

MineviaAC should avoid checking players normally during conditions such as:

* Joining the server
* Respawning
* Teleporting
* Changing worlds
* Being launched by another plugin
* Receiving legitimate knockback
* Explosion knockback
* Entering vehicles
* Leaving vehicles
* Standing in webs
* Climbing ladders
* Swimming
* Being affected by movement potions
* Server TPS drops
* High ping spikes

Important

A flag does not automatically mean a player is cheating.

MineviaAC is intended to help staff identify suspicious behaviour and make the final moderation decision.

Server-side/plugin packet warnings should also not automatically become player violations.

For example, warnings involving invalid entity attachment packets should be investigated separately instead of immediately increasing a player’s VL.

Compatibility

Target:

Minecraft 1.8.8
Minecraft 1.8.9
Spigot/Paper compatible
Java 8+

Plugin Name

MineviaAC

Suggested version:

MineviaAC v1.0

Goal

MineviaAC should be:

Fast. Lightweight. Staff-controlled. Conservative with punishments. Built for Minevia PvP.
