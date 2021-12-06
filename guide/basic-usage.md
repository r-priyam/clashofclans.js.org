---
slug: basic-usage
title: Basic Usage
---

Now that you've installed Node and clashofclans.js, let's start coding!

### Basic Client Usage

```ts
import { Client } from 'clashofclans.js';

const client = new Client({ keys: ['***'] });

(async function () {
    const clan = await client.getClan('#2PP');
    console.log(clan);

    try {
        const data = await client.getPlayer('#2PP');
        console.log(data);
    } catch (error) {
        if (error.reason === 'notFound') {
            console.log('Player not Found!');
        } else {
            console.log(error);
        }
    }
})();
```

### Basic Event Handling

```ts
import { Client } from 'clashofclans.js';
const client = new Client({ keys: ['***'] });

client.on('maintenanceStart', () => {
    console.log('Maintenance started!');
});

client.on('maintenanceEnd', (duration) => {
    console.log('Maintenance ended!', duration);
});

client.on('newSeasonStart', (id) => {
    console.log('New season started!', id);
});

(async function () {
    await client.events.init();
})();
```
