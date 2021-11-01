---
slug: custom-events
title: Custom Events
---

```ts
client.events.addClans(['#8P2QG08P']);
client.events.setEvent({
    type: 'CLAN',
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
