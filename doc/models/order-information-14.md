
# Order Information 14

*This model accepts additional fields of type array.*

## Structure

`OrderInformation14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails5`](../../doc/models/amount-details-5.md) | Optional | - | getAmountDetails(): ?AmountDetails5 | setAmountDetails(?AmountDetails5 amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orderInformation14 = OrderInformation14Builder::init()
    ->amountDetails(
        AmountDetails5Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

