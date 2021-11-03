---
slug: /updating-to-v2
---

# Updating to v2

This new version is a complete TypeScript rewrite to convert everything from plain (literal `JSON {}`) objects to class (constructor) objects and support a lot more features.

### Methods Renamed

All of the methods now have `get` added to the front.

```diff
- client.clan();
+ client.getClan();

- client.player();
+ client.getPlayer();
```

### Get Current War

```diff
- client.currentClanWar();
+ client.getClanWar();

// or

+ client.getCurrentWar();
```

:::caution
The new method `client.getCurrentWar()` returns info about currently running war in the clan for both Regular and CWL Wars.
:::

### Get CWL Group

```diff
- client.clanWarLeague();
+ client.clanWarLeagueGroup();
```

### Get CWL Round

```diff
- client.clanWarLeagueWar();
+ client.clanWarLeagueRound();
```

### Detailed Clan Members

```diff
- const clan = await client.clan('#2PP');
- await client.detailedClanMembers(clan.memberList);

+ const clan = await client.getClan('#2PP');
+ await clan.fetchMembers();
```

### Other Changes

-   To make things simpler `client.verifyPlayerToken()` now returns a boolean value.

-   Param `leagueId` has been removed where it only accepts Legend League Id (29000022).

```diff
- client.leagueSeason(leagueId, [options]);
+ client.getLeagueSeasons([options]);

- client.leagueRanking(leagueId, seasonId, [options])
+ client.getSeasonRankings(seasonId, [options]);
```

- `client.init()` method has been replaced with `client.login()`

## Properties Renamed

### Clan

This includes Clan, Searched Clan, Player Clan, Ranked Clan, War Clan and WarLog Clan.

```diff
- clan.members
+ clan.memberCount

- clan.memberList
+ clan.members

- clan.clanPoints
+ clan.points

- clan.clanLevel
+ clan.level

- clan.clanVersusPoints
+ clan.versusPoints

- clan.requiredTownhallLevel
+ clan.requiredTownHallLevel
```

### Clan Member

```diff
- member.donationsReceived
+ member.received
```

### WarLog, Clan War, CWL Group

**Clan / Opponent**

```diff
- clan.destructionPercentage
+ clan.destruction

- clan.attacks
+ clan.attackCount
```

**Clan War Member**

```diff
- member.townhallLevel
+ member.townHallLevel

- member.opponentAttacks
+ member.defenseCount
```

**Clan War Attack**

```diff
- attack.destructionPercentage
+ attack.destruction
```

### Player

```diff
- player.donationsReceived
+ player.received

- player.warPreference
+ player.warOptedIn // boolean | null
```

### Badge and Icon URLs

```diff
- *.badgeUrls.*
+ *.badge.large
+ *.badge.medium
+ *.badge.small

- *.iconUrls.*
+ *.icon.medium
+ *.icon.small
+ *.icon.tiny
```
