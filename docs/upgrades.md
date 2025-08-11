# Upgrades

Upgrades are a new feature in FactionsUUID, still under active development.

* Upgrades added:
    * Growth boosting. X% chance of Y extra growth steps.
    * DTR claim limit boost. +X claims.
    * Max member boost. +X members.
    * Fall damage reduction. -X% damage.
    * Redstone flood protection - protects redstone from being picked up by water.
    * Max power boost. Increases the maximum cumulative power a faction can have, for large factions.
    * Flight. Now it's an upgrade. If the command is enabled in config, it is (on first start only) default enabled and granted.
    * Zones. Can unlock it all at once or allow +X zones.
    * Shields! Unlock ability to temporarily protect your faction using `/f shield`
* Configure, for now, by editing (while server is stopped) the new `data/universe.json` file. It pre-fills in example values and auto-sets each new upgrade to disabled, so you don't get surprised. Remove it from the disabled list, tweak the values/costs, and off you go!
* New command `/f upgrades` to show upgrades and, if you have the new Permissible Action (`/f set perms`) to upgrade your faction, click the upgrades to buy!
    * Comes with a confirmation before purchasing.
    * Alerts online members when an upgrade is purchased.
* Permission node `factions.upgrades` for viewing upgrades. Might change it later.
    * Default granted to players.
