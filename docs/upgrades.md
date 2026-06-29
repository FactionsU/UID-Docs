# Upgrades

Factions spend money to purchase leveled upgrades that grant lasting perks.

## Available upgrades

* **Armor Durability Protection**
  * Armor and shields lose durability slower while in your territory.
  * -X% durability loss for members and allies.
* **Beacon Effect Control**
  * Control who receives beacon effects in your territory.
  * Controlled with a `/f set perms` permission so you can grant it to anyone.
* **Crop Yield Boost**
  * X% chance to multiply the harvest Y times.
* **DTR Claim Limit Boost**
  * +X maximum claims allowed.
* **DTR Loss Reduction**
  * Lose -X% less DTR when members die.
* **DTR Regeneration Boost**
  * +X% boost to regen rate.
* **Fall Damage Reduction**
  * -X% fall damage.
* **Flight**
  * Enables flight. 
  * If the command is enabled in older config, it is (on first start only) default enabled and granted.
* **Growth**
  * X% chance of Y extra crop growth steps.
* **Max Member Boost**
  * +X members allowed.
* **Max Power Boost**
  * +X maximum allowed cumulative power for the faction.
* **Mob Drop Boost**
  * Mobs killed in your territory have an X% chance to drop Y times the loot.
* **Mob Experience Boost**
  * +X% extra experience from mobs killed in your territory.
* **No Hunger Loss**
  * Members do not lose hunger while in your territory.
* **Power Regeneration Boost**
  * +X% boost to regen rate.
* **Power Loss Reduction**
  * Lose -X% less power when members die.
* **Redstone Flood Protection**
  * Protects redstone from being picked up by water.
* **Shields**
  * Unlock the ability to temporarily protect your faction using `/f shield`.
  * Can be scheduled.
  * Shields last X minutes with Y minute cooldown.
* **Spawner Spawn Rate**
  * -X% spawner delay to next spawn attempt.
* **Territory Damage Boost**
  * Members and allies deal +X% extra damage to players while in your territory.
* **Territory Damage Resistance**
  * Members and allies take -X% damage from players while in your territory.
* **TNT Bank**
  * X TNT maximum in the bank
* **TNT Bank Passive Fill**
  * +X TNT per minute added to the bank.
* **Vaults**
  * Faction vaults using PlayerVaultsX.
  * X vaults allowed
* **Warps**
  * +X faction warps.
* **Zones**
  * A 'zone' can contain one or more claimed chunks, and have special permissions apply to just that region.
  * For example, could create a zone that lets allies build for shared construction.
    * or a zone for only moderators and above to open chests.
  * Unlock it all at once or allow +X zones.


## Buying upgrades

* The `/f upgrades` command shows your upgrades along with their descriptions, status, and cost.
* If you have the Permissible Action to upgrade your faction (granted via `/f set perms`), you can click an upgrade to buy it.
    * Purchasing comes with a confirmation prompt.
    * Online members are alerted when an upgrade is purchased.
* Permission node `factions.upgrades` controls who can view upgrades. It is granted to players by default.

## Configuring upgrades

There are two ways to configure which upgrades are available, their levels, effects, and costs:

* **In game (Paper):** the `/fa upgrades` admin command opens a management menu.
  * Changes are staged and only applied once you review and confirm them. This requires the `factions.upgrades.manage` permission.
* **By file:** edit the `data/universe.json` file while the server is stopped. It
  pre-fills example values and auto-sets each newly added upgrade to disabled, so
  you don't get surprised. Remove an upgrade from the disabled list, tweak its
  values/costs, and off you go!
