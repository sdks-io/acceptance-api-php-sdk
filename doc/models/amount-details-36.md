
# Amount Details 36

*This model accepts additional fields of type array.*

## Structure

`AmountDetails36`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | This field defines the total order amount. | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `currency` | `?string` | Optional | This field defines the currency applicable to the order. | getCurrency(): ?string | setCurrency(?string currency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails36Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails36 = AmountDetails36Builder::init()
    ->totalAmount('21')
    ->currency('USD')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

