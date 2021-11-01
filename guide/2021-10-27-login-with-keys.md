---
slug: login-with-keys
title: Login with Keys
---

To create a client, you need to create an account on [Clash Of Clans API](https://developer.clashofclans.com/#/getting-started).

To login with your own keys, generate the keys by entering your ip with your key options.

### Basic Client

Basic Client that creates connection with your created keys

```ts
// Initialize the API Client
import { Client } from 'clashofclans.js';
const clashClient = new Client({
    keys: ['***']
});
```
