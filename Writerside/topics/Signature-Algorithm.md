# Signature Algorithm

The Signature Algorithm page provides developers with the necessary information to securely sign their API requests to
the UCanPay system. This ensures that the data integrity is maintained, and each request is verified to be from an
authenticated source.

## Purpose

Signing API requests ensures that the payload has not been altered in transit, and it confirms the identity of the
requester. It is a critical component of secure communication with UCanPay APIs.

## Algorithm Used

UCanPay uses RSA encryption for signing requests. Below are the steps to generate a signature with the RSA algorithm.

## Steps to Generate a Signature

1. **Collect the Parameters**: Gather all the required parameters for the API call.
2. **Sort Parameters**: Sort all the parameters alphabetically by their keys.
3. **Concatenate Parameters**: Create a concatenated string of the sorted parameters in the form of `key=value` pairs
   separated by `&`.
4. **Create String to Sign**: Append the API endpoint URI to the concatenated parameters string.
5. **Generate Signature**: Sign the string using your private RSA key.

## Example

```java
import java.security.KeyFactory;
import java.security.PrivateKey;
import java.security.spec.PKCS8EncodedKeySpec;
import java.util.Base64;
import java.security.Signature;

public class SignatureExample {
    public static String signData(String data, String privateKeyStr) throws Exception {
        PKCS8EncodedKeySpec keySpec = new PKCS8EncodedKeySpec(Base64.getDecoder().decode(privateKeyStr));
        KeyFactory keyFactory = KeyFactory.getInstance("RSA");
        PrivateKey privateKey = keyFactory.generatePrivate(keySpec);
        Signature signature = Signature.getInstance("SHA256withRSA");
        signature.initSign(privateKey);
        signature.update(data.getBytes());
        byte[] signatureBytes = signature.sign();
        return Base64.getEncoder().encodeToString(signatureBytes);
    }
}
```

Replace `privateKeyStr` with your actual private key string.

## Troubleshooting

- **Invalid Signature**: Ensure the string to sign is correctly constructed and all parameters are included.
- **Signature Mismatch**: Verify that the private key corresponds to the public key registered with UCanPay.
- **Algorithm Error**: Confirm that SHA256withRSA is the algorithm being used, as this is what UCanPay expects.

- For any further issues with the signature algorithm, contact UCanPay support.