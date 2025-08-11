# Commands

| Command                                                  | Description                                                                         |
|----------------------------------------------------------|-------------------------------------------------------------------------------------|
| /f announce <message>                                    | Send an announcement to all members, including those offline                        |
| /f ban <player>                                          | Ban a player                                                                        |
| /f chat                                                  | Switch between chat types                                                           |
| /f chat ally/coleader/faction/mod/normal/public/truce    | Change chat to the named chat type                                                  |
| /f claim                                                 | Claim the chunk you're standing in                                                  |
| /f claim --auto                                          | Toggle auto-claiming                                                                |
| /f claim --radius [radius]                               | Claim a radius around your position                                                 |
| /f claim --fill --fill-limit [limit]                     | Claim inside a claimed shape                                                        |
| /f claim --faction [faction]                             | Claim for another faction, if allowed                                               |
| /f clear bans                                            | Unban all from your faction                                                         |
| /f clear claims                                          | Unclaim all territory                                                               |
| /f clear invites                                         | Revoke all invites                                                                  |
| /f clear warps                                           | Delete all warps                                                                    |
| /f coords                                                | Broadcast your current position to your faction                                     |
| /f create <tag>                                          | Create a new faction with the given tag                                             |
| /f disband                                               | Disbands your faction                                                               |
| /f fly                                                   | Toggles flight                                                                      |
| /f fly --auto                                            | Toggles auto-flight, starting flight whenever you have permission                   |
| /f fly --trail [trail]                                   | Turns on a particle trail for your flight                                           |
| /f grace                                                 | Checks the status of grace                                                          |
| /f home                                                  | Goes to your faction home                                                           |
| /f home --faction [faction]                              | Goes to another faction's home, if you have permission                              |
| /f invite <player>                                       | Invites a player to join your faction                                               |
| /f invite <player> --delete                              | Revokes an invite                                                                   |
| /f join <faction>                                        | Joins the named faction, if the faction is open or you're invited                   |
| /f kick [target]                                         | Kicks a player                                                                      |
| /f leave                                                 | Leaves your faction                                                                 |
| /f link                                                  | Gets the link your faction has set                                                  |
| /f list                                                  | Lists factions                                                                      |
| /f list factions                                         | Lists factions                                                                      |
| /f list banlist                                          | Lists bans                                                                          |
| /f list claims                                           | Lists your faction's claims                                                         |
| /f list invites                                          | Lists your faction's invites                                                        |
| /f map                                                   | Shows the map                                                                       |
| /f map --auto-on                                         | Turns on auto-map display when crossing chunk boundaries                            |
| /f map --auto-off                                        | Turns off auto-map display                                                          |
| /f map --set-height [height]                             | Sets the map height                                                                 |
| /f money balance                                         | Gets your faction's balance                                                         |
| /f money deposit <amount>                                | Deposits money to your faction                                                      |
| /f money send <amount> to faction <faction>              | Sends faction money to a faction                                                    |
| /f money send <amount> to player <player>                | Sends faction money to a player                                                     |
| /f money withdraw <amount>                               | Withdraws money from your faction                                                   |
| /f near                                                  | Shows nearby faction members                                                        |
| /f power                                                 | Gets your power                                                                     |
| /f power [player]                                        | Gets a player's power                                                               |
| /f relation <faction> ally/enemy/neutral/truce           | Sets your relation with the given faction                                           |
| /f role <member> admin/coleader/moderator/member/recruit | Sets a member's role                                                                |
| /f role <member> promote                                 | Promotes a member one role higher                                                   |
| /f role <member> demote                                  | Demotes a member one role lower                                                     |
| /f set defaultrole <role>                                | Sets the role for new joining member                                                |
| /f set description <desc>                                | Sets the faction description, for the `show` command                                |
| /f set explosions true/false                             | Toggles explosions (if in a peaceful faction)                                       |
| /f set home                                              | Sets the faction home                                                               |
| /f set home --delete                                     | Deletes the faction home entirely                                                   |
| /f set link <url>                                        | Sets the faction link for the `link` command                                        |
| /f set open [state]                                      | Sets if the faction is open to invite-less joins                                    |
| /f set perms                                             | Control permissions in your faction                                                 |
| /f set tag <tag>                                         | Changes the faction's tag                                                           |
| /f set title <player> [title]                            | Sets the title for a player (or deletes, if you provide no title)                   |
| /f set warp <name>                                       | Creates a warp on your position with the given name                                 |
| /f set warp <name> --password [password]                 | Creates a warp on your position with the given name and password                    |
| /f set warp <name> --delete                              | Deletes the named warp                                                              |
| /f set warp-property <name> --password [password]        | Sets a new password for the named warp                                              |
| /f set warp-property <name> --remove-password            | Deletes the named warp's password                                                   |
| /f shield                                                | Checks your faction's shield status                                                 |
| /f shield status                                         | Same as above                                                                       |
| /f shield activate                                       | Activates your faction's shield                                                     |
| /f show                                                  | Shows your faction's info                                                           |
| /f show <faction>                                        | Shows another faction's info                                                        |
| /f status                                                | Shows your status                                                                   |
| /f stuck                                                 | Helps you teleport to safety when in a place you cannot break or place blocks       |
| /f tnt                                                   | Gets the faction's TNT bank size                                                    |
| /f tnt info                                              | Same as above                                                                       |
| /f tnt deposit <amount>                                  | Deposits TNT from your inventory into the faction bank                              |
| /f tnt fill <radius> <amount>                            | Fills a quantity of TNT from your bank into all dispensers within the radius        |
| /f tnt siphon <radius> <amount>                          | Siphons a quantity of TNT from nearby dispensers into your TNT bank                 |
| /f tnt withdraw <amount>                                 | Withdraws TNT from your bank into your inventory                                    |
| /f toggle chat ally                                      | Toggles entirely hiding ally chats, in case an ally is getting too chatty           |
| /f toggle chat truce                                     | Toggles entirely hiding truce chats, in case a truced faction is getting too chatty |
| /f toggle logins                                         | Toggles being notified when a member joins or leaves the server                     |
| /f toggle scoreboard                                     | Toggles the scoreboard being visible                                                |
| /f toggle seechunk                                       | Toggles particle effects at chunk corners for visibility of claims                  |
| /f top                                                   | Rudimentary /f top                                                                  |
| /f unban <player>                                        | Unbans a player                                                                     |
| /f unclaim                                               | Unclaims the chunk you're standing in (see claim command for other flags)           |
| /f unclaim --all-territory                               | Unclaims every single chunk you own                                                 |
| /f upgrades                                              | Opens the upgrades info, including descriptions, status, and purchasing             |
| /f vault <number>                                        | Opens the numbered faction vault (requires PlayerVaultsX)                           |
| /f warp <warp>                                           | Teleports you to a named warp                                                       |
| /f warp <warp> <password>                                | Teleports you to a named warp with a password                                       |
| /f zone create <zone>                                    | Creates a zone                                                                      |
| /f zone claim <zone>                                     | Marks an already-owned chunk as belonging to the named claim                        |
| /f zone delete <zone>                                    | Deletes the named zone                                                              |
| /f zone set <zone> greeting <greeting>                   | Sets the greeting for entering zone territory                                       |
| /f zone set <zone> name <name>                           | Sets a new name for the named zone                                                  |
| /f zone set <zone> perms                                 | Controls permissions for the named zone                                             |

# Admin Commands

| Command                                           | Description                                                                                                    |
|---------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| /fa bypass                                        | Toggles you into or out of bypass mode                                                                         |
| /fa chatspy                                       | Toggles you into or out of listening to internal faction chatter                                               |
| /fa dtr modify <faction> <amount>                 | Modifies the faction's DTR by the given amount                                                                 |
| /fa dtr reset-all                                 | Resets all factions' DTR to their maximum value                                                                |
| /fa dtr set <faction> <amount>                    | Sets the faction's DTR to the given amount                                                                     |
| /fa force disband <faction>                       | Forcibly disbands the given faction                                                                            |
| /fa force home <player>                           | Sends the given player to their faction home                                                                   |
| /fa force kick <player>                           | Forcibly kicks a player from their faction                                                                     |
| /fa money <faction> modify <amount> --notify      | Modifies the given faction's bank balance by the given amount, optionally (with flag) notifying online members |
| /fa money <faction> set <amount> --nofity         | Sets the given faction's bank balance, optionally (with flag) notifying online members                         |
| /fa power boost set faction <faction> <value>     | Sets a faction's power boost to the given value                                                                |
| /fa power boost modify faction <faction> <amount> | Modifies a faction's power boost by the given amount                                                           |
| /fa power boost set player <player> <value>       | Sets a player's power boost to the given value                                                                 |
| /fa power boost modify player <player> <amount>   | Modifies a player's power boost by the given amount                                                            |
| /fa power modify <player> <amount>                | Modifies a player's power by the given amount                                                                  |
| /fa power set <player> <value>                    | Sets a player's power to the given value                                                                       |
| /fa power permanent <faction> <value>             | Sets a faction's power to always be a given value                                                              |
| /fa reload                                        | Reloads configs and lang files (note: some things do still require a full restart)                             |
| /fa save-all                                      | Saves faction data                                                                                             |
| /fa set auto-save true/false                      | Toggles auto-saving of faction data                                                                            |
| /fa set grace off                                 | Turns off grace (explosion protection, typically for start of server)                                          |
| /fa set grace on <duration>                       | Turns on grace for a period of time (e.g. `5d3h` would be 5 days 3 hours)                                      |
| /fa set max-vaults <faction> <amount>             | Sets the max quantity of `/f vault` vaults a faction has (requires PlayerVaultsX)                              |
| /fa set peaceful <faction>                        | Sets a faction to peaceful or removes it if already set                                                        |
| /fa set permanent <faction>                       | Sets a faction's state to permanent (requires no members) or removes it if already set                         |
| /fa set tag <faction> <tag>                       | Changes a faction's tag                                                                                        |
| /fa ticket-info                                   | Gets some basic info to start a help ticket in the support Discord                                             |
| /fa ticket-info --full                            | Gets more advanced info, useful for some tickets in the support Discord                                        |
