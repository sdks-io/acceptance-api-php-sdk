
# Buyer Information 12

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantCustomerId` | `?string` | Optional | Your identifier for the customer.<br><br>**Constraints**: *Maximum Length*: `100` | getMerchantCustomerId(): ?string | setMerchantCustomerId(?string merchantCustomerId): void |
| `email` | `?string` | Optional | Customer's primary email address, including the full domain name.<br><br>**Constraints**: *Maximum Length*: `255` | getEmail(): ?string | setEmail(?string email): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation12 = BuyerInformation12Builder::init()
    ->merchantCustomerId('merchantCustomerID2')
    ->email('email0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

