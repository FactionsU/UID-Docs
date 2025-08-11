# The Big 4.0 Update

!!! warning
    If you run into a problem with 4.0.0, you can revert back to 0.7.8.   
    Note that, because the plugins use two different folders (`plugins/Factions` and `plugins/FactionsUUID`),
    reverting version will be reverting back to the data you had on 0.7.x. 
    Plugin compatibility issues should appear right during startup, though, so you should be able to catch
    this early enough to not matter.  
    Reach out on Discord with any concerns.

[Visit the Support Discord   :simple-discord:](https://discord.gg/PHpuzZS){ .md-button .md-button--primary }

This update is very, *very* large in terms of code. Over 500 files touched, and dozens of _thousands_ of changed lines.
It needs more than a quick, bulleted changelog.


## Plugin Rename and Proper Version

It's about time we properly identified as `FactionsUUID`. And it's about time we had a user-readable version number.

The plugin will now follow [SemVer](https://semver.org/), meaning breaking changes will be clearly labeled by
bumping to version 5 and not snuck into something like 4.0.1 instead.

I'm happy to rant about the reason I leapt to 4.0 instead of 1.0 on Discord.

See [here](#plugin-compatibility) for compatibility concerns.

## Command Overhaul

* Commands now properly offer auto-completion at all steps. 
     * This was a major frustration for users and for me.
* Commands are only visible if the user can actually use them.
    * Don't have the permission? Can't see the command.
    * Not in a faction? Can't see commands only for faction members.
    * Don't have PlayerVaultsX? Can't see `/f vault`.
    * Disabled economy? Can't see the money commands.
* Some commands are now deeper sub-commands instead of dumping everything to the command root.
    * For instance, `/f set description` and `/f set home`
* Administrative commands, for those running the server itself, are moved to `/fa`
    * Stands for `factions admin` I guess.
    * For example, `/fa bypass` or `/fa force disband <faction>`
* Useful, automatically-populated, help command.

### A Few Neat Additions

* Grace
    * Explosion protection for all factions for a period of time, typically at the start of a new server or season.
    * `/f grace`
    * `/fa grace off` or `/fa grace on <duration>`
        * For example, for a 2 day 12 hour grace, `/fa grace on 2d12h`
* Shield
    * Explosion protection for one faction for a period of time.
    * `/f shield` to check, `/f shield activate` to turn on.
    * Server-defined durations, upgradable as the whole thing is an [upgrade](#upgrades).
* Clearing commands
    * `/f clear` lets the faction leadership delete all bans, claims, invites, and warps from one place.
* Scoreboards no longer show useless numbers on the side, when running Paper.
* Significantly improved chat system when running Paper
    * Capable of handling PlaceholderAPI placeholders, faction-coloring, and more.
    * Reach out in Discord for tips as I have not yet built the documentation on this.
* Improved `/f chat` for all. Formatting in config is far more readable and flexible.
* Uses native Adventure when running on Paper.
* Added confirmation to some risky actions, such as disbanding.

## Upgrades

It's finally time for some nice-looking upgrades.

* Introduced new upgrades:
    * Growth boosting.
    * DTR claim limit boost.
    * Max member boost.
    * Fall damage reduction.
    * Redstone flood protection.
    * Max power boost.
    * Flight. 
        * Now it's an upgrade. 
        * If the command is enabled in config, it is (on first start only) default enabled and granted.
    * [Zones](#zones).
    * Shields.
* The `/f upgrades` command uses dialogs, which look nice.
* Admins can define any number of levels for most upgrades.
    * Can define as a map of level number to upgrade value, or can define as an equation.
    * The defaults demonstrate both types.


## Zones

A way to further separate control within a faction's claims. Replaces the previous clunky 'owner' system.

A 'zone' is a collection of faction-claimed chunks that can have their own enter-greeting and their own
permissions. 

Do you want a building in the center of your base that only faction leaders can open chests? Make a zone for that chunk!

Do you want a region where allies can collaboratively build? Make a zone for those chunks!

## Plugin Compatibility

FactionsUUID 4.0.0 changes plugin name and internal naming, too.

This will cause some plugin compatibility issues, which is why I sent reminders to users over many months to let me know
what plugins they're using so I could help migrate.

Plugins that FactionsUUID hooks directly into, and thus should work without issue:  

* Depenizen
* Duels (this is new in 4.0.0)
* dynmap
* EssentialsX
* LuckPerms
* Magic
* PlaceholderAPI
* Sentinel
* Vault
* WorldGuard

**FactionsBridge 1.3.9**, released in August 2025, works with FactionsUUID 4.0.0. Update to this version, if you use
FactionsBridge, to ensure continued support for your plugins that need it.

Other plugins may need updating and, for open source plugins, I'm happy to write pull requests. For closed-source
plugins, developers should reach out on Discord.


## Developer Experience

If you are a plugin dev, this is for you. If not, you've reached the end of the very long update post!

### Dependency Coordinates

We moved! Substantially. Here's the gradle version of it. I trust maven users can sort it out from this.
```kotlin
repositories {
    exclusiveContent {
        forRepository {
            maven("https://dependency.download/releases")
        }

        filter {
            includeGroup("dev.kitteh")
        }
    }
}
dependencies {
    compileOnly("dev.kitteh:factions:4.0.0")
}
```

### Plugin Rename

The plugin is now named `FactionsUUID` - make sure to update your depend/softdepends!

### Package change

Switched to `dev.kitteh.factions` for a clean break from overlapping with other forks.

### API improvements

* API for testing protection just like the plugin does - `Protection` class.
    * I moved a lot of the checks into this class for consistency and convenience.
    * Most were previously testing if something was allowed, but now they test if denied.
    * If you previously used any of the event listener checks, be aware these switched the boolean.
        * Previously it was usually named `justCheck`, meaning `true` would not notify the user.
        * Now it is `notify` meaning `true` *will* notify the user.
* API for adding third-party commands off `/f` - `ThirdPartyCommands` class.
* API for adding upgrades - `UpgradeRegistry` class.
* API for manipulating zones is in `Faction`.
* API for defining 3rd party plugin-provided AFK checks, vanish checks, and chat-ignored checks.
    * Basically, the previously EssX-only checks can be extended. 
* Majorly cleaned up `Board`, `Faction`, and `FPlayer`.
    * Nearly everything the plugin does with those items is now in public API.
    * Went for a bit more fluent API for legibility.
    * Added various helper methods for getting factions.
        * For example: `#!java Factions.factions().getAt(location)`
* Nullness annotations using JSpecify.
