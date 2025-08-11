# Developers

!!! warning "This page contains information only useful to plugin developers"

### Coordinates  
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

## FLocation
FLocation is a Chunk wrapper. If you ever want to deal with the map, claimed land, or something similar, you'll need to
convert a Location or Chunk into an FLocation, both of which are super easy :)

**Getting from a Bukkit Location.**
```java
FLocation flocation = new FLocation(location);
```

**Getting from a Chunk**
```java
FLocation flocation = new FLocation(chunk);
```

## FPlayers
There is always **1** FPlayer object for each player that's been on the server, including online ones. It's very easy to
get the associated FPlayer if you already have the Bukkit Player or their UUID.

**By Bukkit Player**
```java
FPlayer fplayer = FPlayers.fPlayers().get(player);
```

**By UUID**
```java
FPlayer fplayer = FPlayers.fPlayers().get(uuid);
```

**Get Role**
```java
Role fplayerRole = fplayer.role();
``` 

## Factions
There are multiple ways you can get a Faction.

**By name (aka tag)**
```java
Faction faction = Factions.factions().get("name");
```

If you have an FPlayer
```java
Faction faction = fPlayer.faction();
```

If you have a FLocation, you can get the Faction that owns it (including Wilderness, Warzone, and Safezone)
```java
Faction faction = fLocation.faction();
```
