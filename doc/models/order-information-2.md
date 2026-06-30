
# Order Information 2

*This model accepts additional fields of type array.*

## Structure

`OrderInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails3`](../../doc/models/amount-details-3.md) | Optional | - | getAmountDetails(): ?AmountDetails3 | setAmountDetails(?AmountDetails3 amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orderInformation2 = OrderInformation2Builder::init()
    ->amountDetails(
        AmountDetails3Builder::init()
            ->additionalAmount('additionalAmount8')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

