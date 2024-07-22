# Request Guard

Express middleware that validates request parameters against allowed value lists

## Quick Setup

```bash
npm install request-guard
```

Make sure you have `body-parser` set up in your Express app.

## How It Works

```javascript
const guard = require('request-guard');

const allowedStatus = ['active', 'pending', 'archived'];

app.get('/users',
  guard('status', allowedStatus),
  (req, res) => {
    // Only reaches here if status is valid
    res.send('Status check passed!');
  }
);
```

If someone tries `?status=bogus`, they'll get a 400 error explaining which values are allowed.

## Why Use This?

- Stops invalid data early in request chain
- Clean, readable validation rules
- Works with URL params and query strings
- Tiny footprint - no extra dependencies

MIT Licensed - free to use in any project.
