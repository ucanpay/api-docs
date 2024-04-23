# Authentication

Secure access to the UCanPay API requires authentication to ensure that API requests are made by verified users. This section describes how to authenticate API requests using your API keys.

## API Keys

API keys are essential for accessing UCanPay's API securely. You will receive two types of keys when you register your UCanPay account:

- **Public Key**: Used mainly for operations that require client-side integration, such as initializing payment widgets.
- **Private Key**: Used for server-to-server communication. It must be kept confidential and only stored on your servers.

## Using API Keys

You must include your API key as a header in each request to the UCanPay API. The key helps the API identify who is making the request.

Example of including an API key in a request header:

```bash
curl -X POST https://api.ucanpay.com/payment/unifiedorder \
     -H "Authorization: Bearer your_private_key" \
     -H "Content-Type: application/json" \
     -d '{
           "merchantId": "your_merchant_id",
           "outTradeNo": "123456789",
           "totalAmt": 100,
           "currency": "USD",
           "notifyUrl": "https://yourdomain.com/notifications"
         }'
```

## Best Practices for Key Security

- **Do Not Hardcode Keys:** Avoid hardcoding your API keys directly into your applications' code. Instead, use environment variables or configuration files that are not included in your version control system.

- **Limit Permissions:** Use keys that provide the minimum scope of access necessary for the application they support.

- **Rotate Keys Regularly:** Change your API keys periodically to reduce the risk of unauthorized access.

## Handling Errors

If there is an issue with your API key or if it is missing from your request, you will receive an error response. Here's an example of an error response for unauthorized access:

```json
{
    "status": 403,
    "error": "Unauthorized",
    "message": "Invalid API key or token"
}
```

## Next Steps
After setting up authentication, you are ready to explore detailed functionalities offered by the API. Proceed to the sections detailing how to initiate transactions, handle responses, and verify transaction status.

For any questions or issues related to API keys or authentication, please contact our support team at support@ucanpay.com.