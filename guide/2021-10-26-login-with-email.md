---
slug: login-with-email
title: Login with Email
---

To create a client, you need to create an account on [Clash Of Clans API](https://developer.clashofclans.com/#/getting-started).

Use `email` and `password` to start the client and automatically generate API keys.

### Basic Client

Basic Client that creates connection with default values

```ts
// Initialize the API Client
import { Client } from 'clashofclans.js';
const clashClient = new Client();

// Login with email and password
(async function () {
    await clashClient.login({ email: 'email', password: 'password' });
})();
```

### Advanced Client

BatchThrottler: Allows a group of requests to happen every specified time.
For example, 20 requests every second

QueueThrottler: Allows requests to happen every x amount of time.
For example, 1 request every 60 milliseconds

keyName: Name that keys are created with

keyCount: Count of keys that are created

```ts
// Initialize the API Client
import { BatchThrottler, QueueThrottler, Client } from 'clashofclans.js';

// BatchThrottler Example
const clashClient = new Client({
    throttler: new BatchThrottler(30) // value == items per queue group
});

// QueueThrottler Example
const clashClient = new Client({
    throttler: new QueueThrottler(10) // value == millisecond
});

// Login with email and password
(async function () {
    await clashClient.login({
        email: 'email',
        password: 'password',
        keyName: 'API_CLIENT',
        keyCount: 2
    });
})();
```
