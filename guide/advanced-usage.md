---
slug: advanced-usage
title: Advanced Usage
---

Now that we've seen basic client usage, let's look at some advanced usage.

```typescript
// Initialize the API Client
import { Client, BatchThrottler, QueueThrottler } from 'clashofclans.js';

// BatchThrottler Example
const client = new Client({
    cache: true, // enable caching
    retryLimit: 1,
    restRequestTimeout: 5000, // 5 seconds
    throttler: new BatchThrottler(30) // requests per queue group
});

// QueueThrottler Example
const client = new Client({
    cache: true,
    retryLimit: 1,
    restRequestTimeout: 5000, // 5 seconds
    throttler: new QueueThrottler(1000 / 10) // milliseconds
});

// Login with email and password
(async function () {
    await client.login({
        email: '***',
        password: '***',
        keyCount: 2,
        keyName: 'Project_XYZ'
    });
})();
```

:::info
`BatchThrottler` allows a group of requests to happen every second. For example, 30 requests every second.

`QueueThrottler` allows requests to happen every x milliseconds. For example, a single request every 100 milliseconds.
:::

:::caution
The library will revoke any key which matches this `keyName` but does not match the current IP address. To avoid conflict with other projects, use a different `keyName` for each project.
:::
