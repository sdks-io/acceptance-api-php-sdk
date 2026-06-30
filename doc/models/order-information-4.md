
# Order Information 4

*This model accepts additional fields of type array.*

## Structure

`OrderInformation4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails6`](../../doc/models/amount-details-6.md) | Optional | - | getAmountDetails(): ?AmountDetails6 | setAmountDetails(?AmountDetails6 amountDetails): void |
| `lineItems` | [`?(LineItem1[])`](../../doc/models/line-item-1.md) | Optional | - | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem1Builder;

$orderInformation4 = OrderInformation4Builder::init()
    ->amountDetails(
        AmountDetails6Builder::init()
            ->serviceFeeAmount('serviceFeeAmount2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lineItems(
        [
            LineItem1Builder::init()
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            LineItem1Builder::init()
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

