# Chat Formatting

FactionsUUID supports a MiniMessage-based chat solution for intra-faction and inter-faction chat.
Additionally, when running Paper, FactionsUUID's public chat support also supports MiniMessage.

## The `<sender>` Tag

In all FactionsUUID's chat support that uses MiniMessage, the `<sender>` tag is much more than meets the eye.
It supports revealing various information about the player who sent the message and the faction they're in.

| Tag                                      | Description                                                                                            | 
|------------------------------------------|--------------------------------------------------------------------------------------------------------|
| `<sender>`                               | A color-formatted username, contextually containing title (same-faction) or faction name               |
| `<sender:name>`                          | The player's username, without formatting                                                              |
| `<sender:title>`                         | The player's title                                                                                     |
| `<sender:name_and_title>`                | The player's username and their title, or just username if not in a faction                            |
| `<sender:role_name>`                     | The player's role's name                                                                               |
| `<sender:role_prefix>`                   | The player's role's prefix, such as (by default) `+`                                                   |
| `<sender:uuid>`                          | The player's UUID                                                                                      |
| `<sender:power_exact>`                   | The player's current power                                                                             |
| `<sender:power_rounded>`                 | The player's current power, rounded as in-game                                                         |
| `<sender:power_max_exact>`               | The player's max power                                                                                 |
| `<sender:power_max_rounded>`             | The player's max power, rounded as in-game                                                             |
| `<sender:relation_name>`                 | The name of the relationship between the viewer of the message and the player                          |
| `<sender:relation_color>`                | The color of the relationship between the viewer of the message and the player                         |
| `<sender:space_if_faction>`              | A space if the player is in a faction, otherwise nothing                                               |
| `<sender:faction>`                       | The faction the player is in, styled to relation, potentially says 'your faction' for self faction     |
| `<sender:faction:name>`                  | The name of the faction the player is in                                                               |
| `<sender:faction:description>`           | The faction's description                                                                              |
| `<sender:faction:link>`                  | The faction's set link (clickable)                                                                     |
| `<sender:faction:create-date>`           | The faction's creation date                                                                            |
| `<sender:faction:members_total_count>`   | Total membership                                                                                       |
| `<sender:faction:members_online_count>`  | Members online                                                                                         |
| `<sender:faction:members_offline_count>` | Members offline                                                                                        |
| `<sender:faction:id>`                    | Internal ID                                                                                            |
| `<sender:faction:claims_count>`          | Claims owned                                                                                           |
| `<sender:faction:claims_max>`            | Claims attainable                                                                                      |
| `<sender:faction:warps_count>`           | Number of warps                                                                                        |
| `<sender:faction:warps_max>`             | Maximum number of warps                                                                                |
| `<sender:faction:power_exact>`           | Faction's power                                                                                        |
| `<sender:faction:power_rounded>`         | Faction's power, rounded as in-game                                                                    |
| `<sender:faction:power_max_exact>`       | Faction's max power                                                                                    |
| `<sender:faction:power_max_rounded>`     | Faction's max power, rounded as in-game                                                                |
| `<sender:faction:power_boost>`           | Faction's power-boost                                                                                  |
| `<sender:faction:dtr_exact>`             | Deaths 'til Raidable (calculates from power if in power mode)                                          |
| `<sender:faction:dtr_rounded>`           | Deaths 'til Raidable, rounded as in-game (calculates from power if in power mode)                      |
| `<sender:faction:dtr_max_exact>`         | Maximum Deaths 'til Raidable (calculates from power if in power mode)                                  |
| `<sender:faction:dtr_max_rounded>`       | Maximum Deaths 'til Raidable, rounded as in-game (calculates from power if in power mode)              |
| `<sender:faction:dtr_frozen_status>`     | DTR freeze status                                                                                      |
| `<sender:faction:dtr_frozen_time>`       | DTR freeze timer                                                                                       |
| `<sender:faction:raidable>`              | If the faction is raidable based on DTR or power                                                       |
| `<sender:faction:bank_balance>`          | Faction bank balance                                                                                   |
| `<sender:faction:tnt_bank_balance>`      | Faction TNT Bank balance                                                                               |
| `<sender:faction:tnt_bank_max>`          | Faction TNT Bank max balance                                                                           |
| `<sender:faction:allies_count>`          | Number of allies                                                                                       |
| `<sender:faction:allies_max>`            | Maximum allowed number of allies                                                                       |
| `<sender:faction:enemies_count>`         | Number of enemies                                                                                      |
| `<sender:faction:enemies_max>`           | Maximum allowed number of enemies                                                                      |
| `<sender:faction:truces_count>`          | Number of truces                                                                                       |
| `<sender:faction:truces_max>`            | Maximum allowed number of truces                                                                       |
| `<sender:faction:shield_active>`         | If the shield is active or not                                                                         |
| `<sender:faction:shield_status>`         | Shield's current status                                                                                |
| `<sender:faction:shield_remaining>`      | Shield remaining time                                                                                  |
| `<sender:faction:relation_name>`         | Name of relation between viewer and faction                                                            |
| `<sender:faction:relation_color>`        | Color of relation between viewer and faction                                                           |
| `<sender:faction:leader>`                | Leader of the faction. Append any of the above `<sender:thing>` things to the leader for their info    |
| `<sender:standing_in_faction>`           | The same fun features as the above `<sender:faction>`. Add any of the `<sender:faction:thing>` things. |
| `<sender:papi:placeholder_here>`         | Replace `placeholder_here` with any papi placeholder, without the `%`. See below.                      |
| `<sender:papi_open:placeholder_here>`    | Replace `placeholder_here` with any papi placeholder, without the `%`. See below.                      |

### The `papi` and `papi_open` placeholders

These enable you to get any PlaceholderAPI placeholders about the message-sending player. 

For example, `<sender:papi:vault_eco_balance>` for the equivalent of `%vault_eco_balance%`.

The `papi` one is self-closing, so formatting does not bleed into the next item, while `papi_open` continues formatting along.

## Public Chat

The default formats are as follows:

Messages from players in factions:  
`<sender:relation_color><sender:role_prefix><sender:faction:name></sender:relation_color> <<sender:name>> <message>`

Messages from players not in factions:
`<<sender:name>> <message>`

As you can see, these use items from the above table. The `<sender:relation_color>` continues until the faction name is said, and then is closed.

You can customize this with any other placeholders, including PlaceholderAPI ones ([see above](#the-papi-and-papi_open-placeholders)).

## Role and Relation Chats

Internal faction chat and relation chats can be enabled, and have their own formatting configs. They also employ the same MiniMessage conventions as above.
Additionally, the relation chats have `<relation>` and the role chats have `<role>`, as simple tags.