
# Customer 10

*This model accepts additional fields of type array.*

## Structure

`Customer10`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customerId` | `?string` | Optional | Unique identifier for the customer's card and billing information.<br><br>When you use Payment Tokenization or Recurring Billing and you include this value in<br>your request, many of the fields that are normally required for an authorization or credit<br>become optional.<br><br>**NOTE** When you use Payment Tokenization or Recurring Billing, the value for the Customer ID is actually the Visa Acceptance payment token for a customer. This token stores information such as the consumer’s card number so it can be applied towards bill payments, recurring payments, or one-time payments. By using this token in a payment API request, the merchant doesn't need to pass in data such as the card number or expiration date in the request itself. | getCustomerId(): ?string | setCustomerId(?string customerId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$customer10 = Customer10Builder::init()
    ->customerId('customerId8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

