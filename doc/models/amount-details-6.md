
# Amount Details 6

*This model accepts additional fields of type array.*

## Structure

`AmountDetails6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `serviceFeeAmount` | `?string` | Optional | Service fee. Required for service fee transactions.<br><br>**Constraints**: *Maximum Length*: `15` | getServiceFeeAmount(): ?string | setServiceFeeAmount(?string serviceFeeAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails6 = AmountDetails6Builder::init()
    ->serviceFeeAmount('serviceFeeAmount0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

