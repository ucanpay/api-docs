# Client Libraries &amp; SDKs

To facilitate the integration of the UCanPay API into your applications, we provide several client libraries and SDKs.
These tools are designed to simplify the process of coding for different platforms and languages, ensuring that
developers can focus on building features without worrying about the underlying API calls.

## Available Libraries

We currently offer client libraries for the following programming languages:

### Python

- **GitHub Repository**: [UCanPay Python SDK](https://github.com/UCanPay/python-sdk)
- **Installation**:
  ```bash
  pip install ucanpay-sdk
  ```
- **Quick Start**:
  ```Python
  from ucanpay import UCanPay
  
  client = UCanPay(api_key='your_api_key')
  response = client.create_payment(amount=100, currency='USD')
  print(response)
  ```

### Java

- **GitHub Repository**: [UCanPay Java SDK](https://github.com/UCanPay/java-sdk)
- **Installation**:
  ```bash
  mvn install:install-file -Dfile=ucanpay-sdk.jar -DgroupId=com.ucanpay -DartifactId=ucanpay-sdk -Dversion=1.0 -Dpackaging=jar
  ```
- **Quick Start**:
  ```Java
  import com.ucanpay.UCanPay;
  
  UCanPay client = new UCanPay("your_api_key");
  Response response = client.createTransaction(100, "USD");
  System.out.println(response.getStatus());
  ```

### Node.js

- **GitHub Repository**: [UCanPay Node SDK](https://github.com/UCanPay/node-sdk)
- **Installation**:
  ```bash
  npm install ucanpay-sdk
  ```
- **Quick Start**:
  ```Javascript
  const UCanPay = require('ucanpay-sdk');
  const client = new UCanPay({ apiKey: 'your_api_key' });
  client.createPayment({ amount: 100, currency: 'USD' })
      .then(response => console.log(response))
      .catch(error => console.error(error));
  ```

### PHP

- **GitHub Repository**: [UCanPay PHP SDK](https://github.com/UCanPay/php-sdk)
- **Installation**:
  ```bash
  composer require ucanpay/ucanpay-sdk
  ```
- **Quick Start**:
  ```PHP
  require_once('vendor/autoload.php');
  
  $client = new UCanPay\UCanPayClient('your_api_key');
  $response = $client->createPayment(100, 'USD');
  echo $response->status;
  ```