# API Usage Examples

This document provides practical examples of how to use the UCanPay API to accomplish common tasks such as creating a
payment order, querying an order, closing an order, and handling refunds.

## Creating a Payment Order

When you want to create a new payment order through the UCanPay system, you'll use the `Placing Unified Order` API
endpoint. Below is an example of how you might call this API.

```http
POST /payment/unifiedorder HTTP/1.1
Host: api.ucanpay.ca
Content-Type: application/json

{
    "subject": "Latte Coffee",
    "body": "Medium Latte Coffee with Extra Cream",
    "totalAmt": 450,
    "currency": "CAD",
    "notifyUrl": "http://merchantwebsite.com/ucpay/notification",
    "merchantId": "2000000010",
    "sceneType": "JSAPI",
    "nonceStr": "4T7RfE",
    "sign": "GeneratedSignatureBasedOnYourPrivateKey"
}
```

The `nonceStr` and `sign` parameters are unique for each request and should be generated according to the API's
specifications.

## Querying an Order

To query the status of an order, you would use the `Querying Orders` endpoint. Here's how you might structure the
request:

```HTTP
POST /payment/orderquery HTTP/1.1
Host: api.ucanpay.ca
Content-Type: application/json

{
    "merchantId": "2000000010",
    "outTradeNo": "12177525012014070",
    "nonceStr": "9s8df7s9d8",
    "sign": "GeneratedSignatureBasedOnYourPrivateKey"
}

```

Replace `outTradeNo` with your unique order number to receive the current status of the specific order.

## Closing an Order

If a customer cancels their order or if an order times out, you can close it using the `Closing Orders` endpoint:

```HTTP
POST /payment/closeorder HTTP/1.1
Host: api.ucanpay.ca
Content-Type: application/json

{
    "merchantId": "2000000010",
    "outTradeNo": "12177525012014070",
    "nonceStr": "a9s8d7f98",
    "sign": "GeneratedSignatureBasedOnYourPrivateKey"
}
```

Make sure to update the `outTradeNo` with the order number you wish to close.

## Handling Refunds

When you need to initiate a refund, you'll use the `Requesting Refund` endpoint:

```HTTP
POST /payment/refund HTTP/1.1
Host: api.ucanpay.ca
Content-Type: application/json

{
    "merchantId": "2000000010",
    "outTradeNo": "12177525012014070",
    "outRefundNo": "22177525012014070",
    "totalAmt": 450,
    "refundAmt": 450,
    "refundDesc": "Customer Cancelled Order",
    "notifyUrl": "http://merchantwebsite.com/ucpay/refundnotification",
    "nonceStr": "s7d89f7",
    "sign": "GeneratedSignatureBasedOnYourPrivateKey"
}
```

Remember to use the unique `outRefundNo` for the refund transaction.

For the `sign` parameter in each of these examples, you will need to generate a signature as per the
UCanPay's `Signature Algorithm` documentation, typically using your API secret.

Please refer to the official UCanPay documentation for more detailed information on each endpoint, required parameters,
and error handling.