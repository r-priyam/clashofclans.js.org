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
        keyName: 'MyKey'
    });
})();
```

:::info
`BatchThrottler` allows a group of requests to happen every second. For example, 30 requests every second.

`QueueThrottler` allows requests to happen every x milliseconds. For example, 1 request every 100 milliseconds.
:::

:::tip
The library will revoke any keys which match this `keyName` but do not match the current IP address. To avoid conflict with other projects, use different `keyName` for different projects.
:::
