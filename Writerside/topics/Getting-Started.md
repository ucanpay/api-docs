# Getting Started

This section will guide you through the initial setup and fundamental steps necessary to integrate the UCanPay API into
your application. By following these steps, you'll be ready to implement UCanPay's payment solutions seamlessly.

## Prerequisites

Before you begin integrating the UCanPay API, ensure you meet the following prerequisites:

- **Secure Environment**: Your development environment must be secure and capable of making HTTPS requests to external
  servers.
- **UCanPay Account**: You need to have a registered UCanPay account. [Sign up here](https://ucanpay.ca/signup) if you
  don't have one.
- **API Credentials**: Obtain your API keys (public and private keys) from your UCanPay dashboard.

## Configuration

1. **Set up your environment**: Ensure your development environment supports HTTP client capabilities to communicate
   with the UCanPay API.

2. **Install SDK**: If you use a popular programming language, consider using one of our official SDKs to simplify your
   code. SDKs are available for languages like Python, Java, and Node.js. You can download them from
   our [GitHub repository](https://github.com/ucanpay).

   Example of installing the UCanPay Python SDK:

   ```bash
   pip install ucanpay-sdk

3. **Configure your keys**: Set your API keys in your project. It's best to keep these keys secure and not hard-coded
   within your application code.

   ```bash
   import ucanpay
   ucanpay.configure(
       api_key="your_api_key"
   )
   ```

## Making Your First Request

To ensure everything is set up correctly, try making a test API call to create a new payment order. This will not
process a real payment but will simulate the API call.

Example request to create a new payment order:

```bash
curl -X POST https://api.ucanpay.ca/payment/unifiedorder \
     -H "Content-Type: application/json" \
     -d '{
           "merchantId": "your_merchant_id",
           "outTradeNo": "123456789",
           "totalAmt": 100,
           "currency": "USD",
           "notifyUrl": "https://yourdomain.com/notifications"
         }'
```

## Next Steps

After verifying that your setup works as expected by processing a test transaction, you can proceed to explore further
functionalities such as handling notifications, querying order statuses, and managing refunds. Detailed guides and
references for these features are available in subsequent sections of this documentation.

For comprehensive information on all available API endpoints and their parameters, refer to the API Reference section.