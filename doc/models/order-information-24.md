
# Order Information 24

*This model accepts additional fields of type array.*

## Structure

`OrderInformation24`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails26`](../../doc/models/amount-details-26.md) | Optional | - | getAmountDetails(): ?AmountDetails26 | setAmountDetails(?AmountDetails26 amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orderInformation24 = OrderInformation24Builder::init()
    ->amountDetails(
        AmountDetails26Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->subTotalAmount('subTotalAmount0')
            ->handlingAmount('handlingAmount2')
            ->shippingAmount('shippingAmount6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

