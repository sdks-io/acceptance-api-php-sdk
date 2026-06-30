
# Post Payment Credentials Request

*This model accepts additional fields of type array.*

## Structure

`PostPaymentCredentialsRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentCredentialType` | `?string` | Optional | The type of payment credentials to be returned.<br>By default, payment credentials include network token and cryptogram or dynamic CVV.<br>If "NETWORK_TOKEN" is supplied then only network token card number will be returned and no cryptogram or dynamic CVV will be requested.<br>If "SECURITY_CODE" is supplied then dynamic CVV will be requested and returned with the network token card number. Dynamic CVV is only supported for Amex and SCOF.<br>If "CRYPTOGRAM" is supplied then cryptogram will be requested and returned with the network token card number. Cryptogram is NOT supported for Amex.<br><br>Possible Values:<br><br>- NETWORK_TOKEN<br>- SECURITY_CODE<br>- CRYPTOGRAM | getPaymentCredentialType(): ?string | setPaymentCredentialType(?string paymentCredentialType): void |
| `transactionType` | `?string` | Optional | Specifies the type of transaction for which the network token credentials are required.<br>Possible Values:<br><br>- ECOM: Ecommerce transaction. If transactionType is not provided, ECOM is set as the default.<br>- AFT: Account Funding Transaction. This is only supported for VISA and paymentCredentialType of CRYPTOGRAM. | getTransactionType(): ?string | setTransactionType(?string transactionType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PostPaymentCredentialsRequestBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$postPaymentCredentialsRequest = PostPaymentCredentialsRequestBuilder::init()
    ->paymentCredentialType('paymentCredentialType8')
    ->transactionType('transactionType2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

