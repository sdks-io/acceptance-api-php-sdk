
# Amex Additional Amount

*This model accepts additional fields of type array.*

## Structure

`AmexAdditionalAmount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Additional amount type. This field is supported only for **American Express Direct**.<br><br>**Constraints**: *Maximum Length*: `3` | getCode(): ?string | setCode(?string code): void |
| `amount` | `?string` | Optional | Additional amount. This field is supported only for **American Express Direct**.<br><br>**Constraints**: *Maximum Length*: `12` | getAmount(): ?string | setAmount(?string amount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmexAdditionalAmountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amexAdditionalAmount = AmexAdditionalAmountBuilder::init()
    ->code('code6')
    ->amount('amount0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

