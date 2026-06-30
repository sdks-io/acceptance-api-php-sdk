
# E Wallet 7

*This model accepts additional fields of type array.*

## Structure

`EWallet7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | The ID of the customer, passed in the return_url field by PayPal after customer approval.<br><br>**Constraints**: *Maximum Length*: `26` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eWallet7 = EWallet7Builder::init()
    ->accountId('accountId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

