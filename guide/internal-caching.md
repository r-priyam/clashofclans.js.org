---
slug: /internal-caching
title: Internal Caching
---

This is based on the [Cache-Control](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control) headers returned by the API. If internal caching is enabled, objects will be cached automatically by the client until they are stale. By default, this is disabled.

## Enable Caching

```ts
import { Client } from 'clashofclans.js';

const client = new Client({ cache: true, keys: ['***'] });
```

## Caching Duration

Some major routes and their `maxAge` values.

|                  Route                   | Value <br/>(seconds) |
| :--------------------------------------: | :------------------: |
|            `/clans/:clanTag`             |         120          |
|          `/players/:playerTag`           |          60          |
|         `/clans/:clanTag/warlog`         |         600          |
|       `/clans/:clanTag/currentwar`       |         600          |
| `/clans/:clanTag/currentwar/leaguegroup` |         600          |
|      `/clanwarleagues/wars/:warTag`      |         600          |
