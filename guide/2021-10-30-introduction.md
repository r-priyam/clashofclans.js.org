---
slug: introduction
title: Introduction
date: 2021-10-31T00:00:00.000Z
---

If you're reading this, it probably means you want to learn how to use clashofclans.js. Let's dig in!

### Installation

To use clashofclans.js, you'll need to install [Node.js](https://nodejs.org/) v14.0.0 or higher version.

```shell
npm i clashofclans.js
```

The next step is to start coding! But before you start, open the [Clash of Clans API Developer Portal](https://developer.clashofclans.com/#/) and go to the "My Account" page to create or copy your keys.

:::info
To create an API Key you'll need your public IP address.
<button onClick={async () => {
    const ip = await fetch('https://api.ipify.org/').then((res) => res.text());
    alert(`Your public IP address is ${ip}`);
}}>Get Your Public IP</button>
:::

:::tip
Alternatively, you can use the developer site email and password to create or retrieve your API keys automatically with clashofclans.js library. [Learn how?](/guide/login-with-email)
:::
