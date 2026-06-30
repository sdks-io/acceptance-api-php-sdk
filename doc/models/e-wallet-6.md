
# E Wallet 6

*This model accepts additional fields of type array.*

## Structure

`EWallet6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | The ID of the customer, passed in the return_url field by PayPal after customer approval.<br><br>**Constraints**: *Maximum Length*: `30` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet6 = EWallet6Builder::init()
    ->accountId('accountId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

