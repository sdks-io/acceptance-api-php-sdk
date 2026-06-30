
# Issuer 4

*This model accepts additional fields of type array.*

## Structure

`Issuer4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentAccountReference` | `?string` | Optional, Read-only | This reference number serves as a link to the cardholder account and to all transactions for that account.<br><br>**Constraints**: *Maximum Length*: `32` | getPaymentAccountReference(): ?string | setPaymentAccountReference(?string paymentAccountReference): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Issuer4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuer4 = Issuer4Builder::init()
    ->paymentAccountReference('paymentAccountReference2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

