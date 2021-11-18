---
slug: custom-events
title: Custom Events
---

Custom events give you absolute freedom in your creativity. Let's look at a simple example which emits a custom event.


```ts
import { Client } from 'clashofclans.js';
const client = new Client({ keys: ['***'] });

client.events.addClans(['#8P2QG08P']);
client.events.setClanEvent({
    name: 'clanDescriptionChange',
    filter: (oldClan, newClan) => {
        return oldClan.description !== newClan.description;
    }
});

client.on('clanDescriptionChange', (oldClan, newClan) => {
    console.log(oldClan.description, newClan.description);
});

(async function () {
    await client.events.init();
})();
```
