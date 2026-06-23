# Placeholders

!!! note "Looking for PlaceholderAPI placeholders? [Click here](placeholderapi.md)"

The MiniMessage placeholders are available in some messages in `translations.conf` such as:

* The scoreboards
* The tooltips
* The `/f list factions` (aka `/f list`) command
* The `/f show` command

In all these cases, the placeholders are resolved from the perspective of the player receiving them, coloring based
on relation or hiding vanished players from the online count.

!!! note "Dynmap Placeholders"
    Other than a few documented-in-file placeholders that are custom to dynmap, you can use the faction placeholder like this:
    `%%<faction>%%` or `%%<faction:name>%%` or other placeholders like that. This is just done to avoid trying to process html as
    MiniMessage.

## The Player Tag

In all FactionsUUID's message support that uses MiniMessage, the player tag is much more than meets the eye.
It supports revealing various information about the player and the faction they're in.

Note: Usually this tag is `<player>` but in chat is `<sender>` instead.

| Tag                                   | Description                                                                                        | 
|---------------------------------------|----------------------------------------------------------------------------------------------------|
| `<player>`                            | A color-formatted username, contextually containing title (same-faction) or faction name           |
| `<player:name>`                       | The player's username, without formatting                                                          |
| `<player:title>`                      | The player's title                                                                                 |
| `<player:name_and_title>`             | The player's username and their title, or just username if not in a faction                        |
| `<player:role_name>`                  | The player's role's name                                                                           |
| `<player:role_prefix>`                | The player's role's prefix, such as (by default) `+`                                               |
| `<player:last_seen>`                  | How long ago the player was last seen, such as "5 hours, 3 minutes"                                |
| `<player:tooltip>`                    | Hover tooltip for the player's info (closeable)                                                    |
| `<player:uuid>`                       | The player's UUID                                                                                  |
| `<player:power_exact>`                | The player's current power                                                                         |
| `<player:power_rounded>`              | The player's current power, rounded as in-game                                                     |
| `<player:power_max_exact>`            | The player's max power                                                                             |
| `<player:power_max_rounded>`          | The player's max power, rounded as in-game                                                         |
| `<player:kills>`                      | The player's kills                                                                                 |
| `<player:deaths>`                     | The player's deaths                                                                                |
| `<player:relation_name>`              | The name of the relationship between the viewer of the message and the player                      |
| `<player:relation_color>`             | The color of the relationship between the viewer of the message and the player (closeable)         |
| `<player:space_if_faction>`           | A space if the player is in a faction, otherwise nothing                                           |
| `<player:scoreboard_map:#>`           | A line of the scoreboard map, as defined in config. Replace `#` with line number.                  |
| `<player:faction>`                    | Gets the player's faction. Can use additional tag info like below, such as `<player:faction:id>`   |
| `<player:standing_in_faction>`        | Gets the faction owning the land the player is in. Add any of the `<player:faction:thing>` things. |
| `<player:papi:placeholder_here>`      | Replace `placeholder_here` with any papi placeholder, without the `%`. See below.                  |
| `<player:papi_mini:placeholder_here>` | Replace `placeholder_here` with any papi placeholder, without the `%`. See below.                  |
| `<player:papi_open:placeholder_here>` | Replace `placeholder_here` with any papi placeholder, without the `%`. See below.                  |


## The Faction Tag



| Tag                               | Description                                                                                         |
|-----------------------------------|-----------------------------------------------------------------------------------------------------|
| `<faction>`                       | The faction the player is in, styled to relation, potentially says 'your faction' for self faction  |
| `<faction:name>`                  | The name of the faction the player is in                                                            |
| `<faction:description>`           | The faction's description                                                                           |
| `<faction:link>`                  | The faction's set link (clickable)                                                                  |
| `<faction:creation_date>`         | The faction's creation date                                                                         |
| `<faction:members_total_count>`   | Total membership                                                                                    |
| `<faction:members_online_count>`  | Members online                                                                                      |
| `<faction:members_offline_count>` | Members offline                                                                                     |
| `<faction:tooltip>`               | Hover tooltip for faction info (closeable)                                                          |
| `<faction:id>`                    | Internal ID                                                                                         |
| `<faction:claims_count>`          | Claims owned                                                                                        |
| `<faction:claims_max>`            | Claims attainable                                                                                   |
| `<faction:claims_value>`          | Claims value                                                                                        |
| `<faction:claims_refund>`         | Claims value of refund                                                                              |
| `<faction:warps_count>`           | Number of warps                                                                                     |
| `<faction:warps_max>`             | Maximum number of warps                                                                             |
| `<faction:power_exact>`           | Faction's power                                                                                     |
| `<faction:power>`                 | Faction's power, rounded as in-game                                                                 |
| `<faction:power_max_exact>`       | Faction's max power                                                                                 |
| `<faction:power_max>`             | Faction's max power, rounded as in-game                                                             |
| `<faction:power_boost>`           | Faction's power-boost                                                                               |
| `<faction:dtr_exact>`             | Deaths 'til Raidable (calculates from power if in power mode)                                       |
| `<faction:dtr_rounded>`           | Deaths 'til Raidable, rounded as in-game (calculates from power if in power mode)                   |
| `<faction:dtr_max_exact>`         | Maximum Deaths 'til Raidable (calculates from power if in power mode)                               |
| `<faction:dtr_max_rounded>`       | Maximum Deaths 'til Raidable, rounded as in-game (calculates from power if in power mode)           |
| `<faction:dtr_frozen_status>`     | DTR freeze status                                                                                   |
| `<faction:dtr_frozen_time>`       | DTR freeze timer                                                                                    |
| `<faction:raidable>`              | If the faction is raidable based on DTR or power                                                    |
| `<faction:bank_balance>`          | Faction bank balance                                                                                |
| `<faction:tnt_bank_balance>`      | Faction TNT Bank balance                                                                            |
| `<faction:tnt_bank_max>`          | Faction TNT Bank max balance                                                                        |
| `<faction:allies_count>`          | Number of allies                                                                                    |
| `<faction:allies_max>`            | Maximum allowed number of allies                                                                    |
| `<faction:enemies_count>`         | Number of enemies                                                                                   |
| `<faction:enemies_max>`           | Maximum allowed number of enemies                                                                   |
| `<faction:truces_count>`          | Number of truces                                                                                    |
| `<faction:truces_max>`            | Maximum allowed number of truces                                                                    |
| `<faction:shield_active>`         | If the shield is active or not                                                                      |
| `<faction:shield_status>`         | Shield's current status                                                                             |
| `<faction:shield_remaining>`      | Shield remaining time                                                                               |
| `<faction:relation_name>`         | Name of relation between viewer and faction                                                         |
| `<faction:relation_color>`        | Color of relation between viewer and faction                                                        |
| `<faction:leader>`                | Leader of the faction. Append any of the above `<player:thing>` things to the leader for their info |
| `<faction:if_permanent>`          | Closeable if statement, only showing inside the statement if faction is permanent                   |
| `<faction:if_peaceful>`           | Closeable if statement, only showing inside the statement if faction is peaceful                    |
| `<faction:if_open>`               | Closeable if statement, only showing inside the statement if faction is open to joining             |
| `<faction:if_raidable>`           | Closeable if statement, only showing inside the statement if faction is raidable                    |
| `<faction:if_online>`             | Closeable if statement, only showing inside the statement if faction has online players             |
| `<faction:if_offline>`            | Closeable if statement, only showing inside the statement if faction has offline players            |
| `<faction:if_allies>`             | Closeable if statement, only showing inside the statement if faction has allies                     |
| `<faction:if_enemies>`            | Closeable if statement, only showing inside the statement if faction has enemies                    |
| `<faction:if_truces>`             | Closeable if statement, only showing inside the statement if faction has truces                     |
| `<faction:if_leader>`             | Closeable if statement, only showing inside the statement if faction has a leader                   |
| `<faction:if_has_home>`           | Closeable if statement, only showing inside the statement if faction has a home                     |

## General Placeholders

These run in nearly every single situation MiniMessage is used.

| Tag                                      | Description                                                                               |
|------------------------------------------|-------------------------------------------------------------------------------------------|
| `<fuuid:title>`                          | Turns the text inside (between open/close tags) into a title, according to the config     |
| `<fuuid:players_count_online>`           | Total count of players online                                                             |
| `<fuuid:players_factionless_online>`     | Total count of factionless players online                                                 |
| `<fuuid:players_factionless_total>`      | Total count of factionless players tracked                                                |
| `<fuuid:players_faction_members_online>` | Total count of faction-having players online                                              |
| `<fuuid:players_faction_members_total>`  | Total count of faction-having players tracked                                             |
| `<fuuid:players_tracked_total>`          | Total count of players tracked                                                            |
| `<fuuid:color:relation:member>`          | Colors text inside (between open/close tags) to the member color                          |
| `<fuuid:color:relation:ally>`            | Colors text inside (between open/close tags) to the ally color                            |
| `<fuuid:color:relation:truce>`           | Colors text inside (between open/close tags) to the truce color                           |
| `<fuuid:color:relation:enemy>`           | Colors text inside (between open/close tags) to the enemy color                           |
| `<fuuid:color:relation:neutral>`         | Colors text inside (between open/close tags) to the neutral color                         |
| `<fuuid:color:role:admin>`               | Colors text inside (between open/close tags) to the admin color                           |
| `<fuuid:color:role:coleader>`            | Colors text inside (between open/close tags) to the coleader color                        |
| `<fuuid:color:role:moderator>`           | Colors text inside (between open/close tags) to the moderator color                       |
| `<fuuid:color:role:member>`              | Colors text inside (between open/close tags) to the regular member color                  |
| `<fuuid:color:role:recruit>`             | Colors text inside (between open/close tags) to the recruit color                         |
| `<fuuid:color:peaceful>`                 | Colors text inside (between open/close tags) to the peaceful color                        |
| `<fuuid:color:safezone>`                 | Colors text inside (between open/close tags) to the safezone color                        |
| `<fuuid:color:warzone>`                  | Colors text inside (between open/close tags) to the warzone color                         |
| `<fuuid:color:wilderness>`               | Colors text inside (between open/close tags) to the wilderness color                      |
| `<fuuid:if_economy>`                     | Closeable if statement, only showing inside the statement if economy is enabled           |
| `<fuuid:if_banks>`                       | Closeable if statement, only showing inside the statement if banks are enabled            |
| `<fuuid:if_perm:PERMISSION>`             | Closeable if statement, only showing inside the statement if the player has the perm node |


### The `papi`, `papi_open`, and `papi_mini` placeholders

These enable you to get any PlaceholderAPI placeholders about the player.

For example, `<player:papi:vault_eco_balance>` for the equivalent of `%vault_eco_balance%`.

The `papi` one is self-closing, so formatting does not bleed into the next item, while `papi_open` applies the formatting onward.
(Developer description: `papi` is self-closing and `papi_open` is not.)

Needing to process MiniMessage input? Use `papi_mini`.

### The `if` placeholders

For the placeholders that start with `if` such as `if_permanent`, the value inside will only display if true. 

For example, `<faction:if_permanent>Permanent</faction:if_permanent>` will only display "Permanent" if the faction is permanent.

Each of these also will handle the opposite condition by adding `:else` to the end.

For example, `<faction:if_permanent:else>Not permanent</faction:if_permanent:else>` will only display "Not permanent" if the faction is not permanent.

## Special `/f show` placeholders.

These special variables will replace their spot in `/f show` and, as necessary, add additional
lines to the message to continue adding more of what they output.

| Variable       | Explanation                             |
|----------------|-----------------------------------------|
| {allies-list}  | Lists each faction ally with tooltips   |
| {enemies-list} | Lists each faction enemy with tooltips  |
| {online-list}  | Lists all online members with tooltips  |
| {offline-list} | Lists all offline members with tooltips |

!!! warning "Legacy variables below"
    Below this line are legacy variables that only work in one or two remaining places while finishing transitioning them out.

Player variables.

| Variable               | Explanation                                                    |
|------------------------|----------------------------------------------------------------|
| {name}                 | Players name                                                   |
| {lastSeen}             | Last time player was seen (if offline), or just 'Online'       |
| {balance}              | Players balance                                                |
| {player-kills}         | # of kills the player has                                      |
| {player-deaths}        | # of deaths the player has                                     |
| {player-power}         | Current player power                                           |
| {player-maxpower}      | Player max power                                               |
| {total-online-visible} | # of players online from the perspective of the current player |

Faction variables. Can be used in tooltips.list, scoreboards, or /f show

| Variable                 | Explanation                                                                    |
|--------------------------|--------------------------------------------------------------------------------|
| {header}                 | Default factions header (ex. /f show)                                          |
| {faction}                | Factions tag (if none, uses lang.yml for factionless name)                     |
| {faction-relation-color} | Factions color relative to the viewer                                          |
| {joining}                | How to join this faction                                                       |
| {power}                  | Factions deaths until raidable value                                           |
| {power-boost}            | DTR Symbol based on current DTR (max, regen, frozen, raidable)                 |
| {maxPower}               | Factions max deaths until raidable value                                       |
| {chunks}                 | # of claims faction has (in chunks)                                            |
| {warps}                  | # of warps faction has                                                         |
| {description}            | Factions description                                                           |
| {create-date}            | Date faction was created                                                       |
| {leader}                 | Faction leader                                                                 |
| {land-value}             | Value of all claims                                                            |
| {land-refund}            | Calculated refund value                                                        |
| {allies}                 | # of allies faction has                                                        |
| {enemies}                | # of enemies faction has                                                       |
| {online}                 | # of faction members online                                                    |
| {offline}                | # of faction members offline                                                   |
| {members}                | # of faction members (includes offline)                                        |
| {faction-balance}        | Faction bank balance                                                           |
| {world}, {x}, {y}, {z}   | Faction home variables. You don't need to use them all.                        |
| {faction-kills}          | # of kills the faction has                                                     |
| {faction-deaths}         | # of deaths the faction has                                                    |
| {faction-bancount}       | # of bans the faction has                                                      |
| {raidable}               | Displays true/false (modifiable in lang.yml)                                   |
| {dtr}                    | Current faction DTR                                                            |
| {max-dtr}                | Max faction DTR based on players                                               |
| {max-chunks}             | Maximum claims the faction can have (power or DTR)                             |
| {peaceful}               | Displays a message if peaceful                                                 |
| {permanent}              | Displays a message if permanent                                                |
| {dtr-frozen-status}      | True or false (customizable in lang.yml) for DTR frozen state                  |
| {dtr-frozen-time}        | Time remaining in frozen state (configure in main.conf) or blank if not frozen |
| {tnt-balance}            | TNT bank balance                                                               |
| {tnt-max-balance}        | Maximum TNT bank balance                                                       |
| {faction-link}           | Faction link from `/f link`                                                    |

Faction Permissions GUI variables. Can only be used in GUI

| Variable              | Explanation                                              |
|-----------------------|----------------------------------------------------------|
| {relation}            | Shows relation name (Can be used in action and relation) |
| {relation-color}      | Relation color                                           |
| {action}              | Shows action name (Can only be used in action)           |
| {action-access}       | Shows the action's access with current relation          |
| {action-access-color} | Access color                                             |

General variables. Can be used anywhere.

| Variable            | Explanation                             |
|---------------------|-----------------------------------------|
| {total-online}      | Total # of players on the server        |
| {max-warps}         | Max # of warps a faction can set        |
| {max-allies}        | Max # of allies a faction can have      |
| {max-enemies}       | Max # of enemies a faction can have     |
| {factionless}       | Count of all factionless players online |
| {factionless-total} | Count of all factionless players online |
