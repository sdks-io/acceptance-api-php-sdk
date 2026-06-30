
# Bonuse

*This model accepts additional fields of type array.*

## Structure

`Bonuse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `month` | `?string` | Optional | This value is a 2-digit code indicating the first bonus month. Valid value from 1 to 12.<br><br>**Constraints**: *Maximum Length*: `2` | getMonth(): ?string | setMonth(?string month): void |
| `amount` | `?string` | Optional | This value contains the bonus amount of the first month. Maximum value without decimal 99999999.<br><br>**Constraints**: *Maximum Length*: `8` | getAmount(): ?string | setAmount(?string amount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BonuseBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bonuse = BonuseBuilder::init()
    ->month('month8')
    ->amount('amount0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

