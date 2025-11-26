# Chat Formatting

FactionsUUID supports a MiniMessage-based chat solution for intra-faction and inter-faction chat.
Additionally, when running Paper, FactionsUUID's public chat support also supports MiniMessage.

## Placeholders

All of the chat has a `<sender>` placeholder. Visit the [placeholders](placeholders.md) page for more info on the
player placeholder, which is simply called "sender" here instead.

## Public Chat

The default formats are as follows:

Messages from players in factions:  
`<sender:relation_color><sender:role_prefix><sender:faction:name></sender:relation_color> <<sender:name>> <message>`

Messages from players not in factions:
`<<sender:name>> <message>`

As you can see, these use items from the above table. The `<sender:relation_color>` continues until the faction name is said, and then is closed.

You can customize this with any other placeholders, including PlaceholderAPI ones.

## Role and Relation Chats

Internal faction chat and relation chats can be enabled, and have their own formatting configs. They also employ the same MiniMessage conventions as above.
Additionally, the relation chats have `<relation>` and the role chats have `<role>`, as simple tags.
