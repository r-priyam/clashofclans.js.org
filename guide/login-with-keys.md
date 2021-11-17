---
slug: login-with-keys
title: Login with Keys
---

:::info
Before you start, you need to create an account on [Clash of Clans API Developer Portal](https://developer.clashofclans.com/#/).

To login with your own keys, generate the keys by entering a key name, description and your public IP address with your key options.

<button onClick={async () => {
    const ip = await fetch('https://api.ipify.org/').then((res) => res.text());
    alert(`Your public IP address is ${ip}`);
    navigator.clipboard.writeText(ip);
}}>Get Your Public IP</button>
:::

```ts
import { Client } from 'clashofclans.js';
const client = new Client({ keys: ['***'] });

// or
client.setKeys(['***']);
```
