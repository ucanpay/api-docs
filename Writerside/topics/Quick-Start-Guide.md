# Quick Start Guide

Welcome to the UCanPay Quick Start Guide. This guide is designed to help you make your first API call and understand the
flow of a typical UCanPay payment process.

## Step 1: Set Up Your Development Environment

Before making your first API call:

- Ensure that you have the [latest version of Node.js](https://nodejs.org/en/download/) installed if you're using
  JavaScript.
- For other languages, make sure you have the relevant environment and HTTP client ready.

## Step 2: Obtain Your API Keys

Log in to your UCanPay account and navigate to the API section to find your API keys. You'll need the `public_key`
and `secret_key` for making API calls.

## Step 3: Make Your First API Call

The following is an example of a simple API call to the UCanPay API to create a new payment order:

```bash
curl -X POST https://api.ucanpay.com/v1/payments \
-H "Content-Type: application/json" \
-H "Authorization: Bearer YOUR_SECRET_KEY" \
-d '{
    "amount": 1000,
    "currency": "USD",
    "description": "Test payment"
}'
```

Replace `YOUR_SECRET_KEY` with your actual secret key.

## Step 4: Handle the API Response

The API will respond with JSON-formatted data. Here's how to handle it:

```Javascript
// Example using Node.js

const https = require('https');

const data = JSON.stringify({
  amount: 1000,
  currency: "USD",
  description: "Test payment"
});

const options = {
  hostname: 'api.ucanpay.com',
  port: 443,
  path: '/v1/payments',
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Content-Length': data.length,
    'Authorization': 'Bearer YOUR_SECRET_KEY'
  }
};

const req = https.request(options, (res) => {
  console.log(`statusCode: ${res.statusCode}`);

  res.on('data', (d) => {
    process.stdout.write(d);
  });
});

req.on('error', (e) => {
  console.error(e);
});

req.write(data);
req.end();
```

## Step 5: Next Steps

After receiving a successful response, you can:

- Check the transaction status.
- Implement webhook listeners for payment events.
- Start integrating UCanPay payment options into your checkout flow.

## Help and Support

If you need help or have questions during this process, please visit our Support & Community section or check out the
User Guides.

Start building with UCanPay today and make payments easy for your customers!