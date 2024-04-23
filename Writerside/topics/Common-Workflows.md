# Common Workflows

This section outlines several common workflows that developers might use when integrating with the UCanPay API. These workflows are designed to guide you through typical use cases, from simple payment processing to more complex transaction management.

## Workflow 1: Processing a Payment

Processing a payment is a fundamental function of the UCanPay API. Here’s a step-by-step guide:

1. **Create a Payment Order**
    - Use the `POST /payment/unifiedorder` endpoint to initiate a payment.
    - Required details include the transaction amount, currency, and merchant identifier.

2. **Customer Authorization**
    - Redirect the customer to the payment gateway using the URL provided in the response of the Unified Order Placement.
    - The customer will authorize the payment and may need to enter payment details depending on the setup.

3. **Payment Confirmation**
    - After payment authorization, UCanPay will redirect back to your specified return URL.
    - A payment notification will be sent to your server's webhook endpoint.

4. **Verify Payment Status**
    - Call the `GET /payment/status` endpoint with the order ID to verify the payment status and ensure it was processed successfully.

## Workflow 2: Refunding a Transaction

Refunding a transaction may be necessary due to customer returns or order cancellations.

1. **Send a Refund Request**
    - Use the `POST /payment/refund` endpoint to initiate a refund.
    - Include the original transaction ID and the amount to be refunded.

2. **Check Refund Status**
    - Use the `GET /payment/refund/status` endpoint to check the status of the refund.
    - Ensure the refund has been processed successfully, or handle errors as needed.

## Workflow 3: Recurring Payments

Setting up recurring payments can facilitate subscriptions and other regular transactions.

1. **Create a Subscription**
    - Use the `POST /subscriptions/create` endpoint to set up a new subscription.
    - Define the billing frequency, amount, start date, and customer details.

2. **Handle Subscription Notifications**
    - Implement webhook endpoints to receive notifications about subscription status updates, such as renewals or cancellations.

3. **Manage Subscription**
    - Use endpoints like `POST /subscriptions/cancel` or `POST /subscriptions/update` to manage existing subscriptions based on user actions or business needs.

## Workflow 4: Handling Errors

Proper error handling ensures a smoother experience for users and easier debugging for developers.

1. **Understand Error Codes**
    - Familiarize yourself with the common error codes that UCanPay API might return (detailed in the Error Handling section).

2. **Implement Error Handling**
    - In your API calls, implement error handling that catches and logs errors.
    - Provide meaningful error messages to users when something goes wrong.

3. **Retry Mechanism**
    - For recoverable errors, implement a retry mechanism that attempts the request again before failing.

By following these common workflows, developers can ensure they are using the UCanPay API effectively and handling different scenarios appropriately. For more detailed information on each endpoint mentioned in these workflows, refer to the API Endpoints section.
