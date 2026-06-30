
# Merchant Information 7

*This model accepts additional fields of type array.*

## Structure

`MerchantInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `transactionLocalDateTime` | `?string` | Optional | Local Time of the transaction<br>Set the timestamp for the exchange rate by ISO 8601 UTC format.<br>Format: “YYYYMMdd’T’HHmmss’Z’”  (20151103T123456Z)<br><br>**Constraints**: *Maximum Length*: `16` | getTransactionLocalDateTime(): ?string | setTransactionLocalDateTime(?string transactionLocalDateTime): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantInformation7 = MerchantInformation7Builder::init()
    ->transactionLocalDateTime('transactionLocalDateTime8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

