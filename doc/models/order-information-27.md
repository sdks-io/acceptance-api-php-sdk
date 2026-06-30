
# Order Information 27

*This model accepts additional fields of type array.*

## Structure

`OrderInformation27`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails29`](../../doc/models/amount-details-29.md) | Optional | - | getAmountDetails(): ?AmountDetails29 | setAmountDetails(?AmountDetails29 amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails29Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orderInformation27 = OrderInformation27Builder::init()
    ->amountDetails(
        AmountDetails29Builder::init()
            ->totalAmount('totalAmount4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

