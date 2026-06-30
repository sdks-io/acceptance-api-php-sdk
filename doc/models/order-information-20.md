
# Order Information 20

*This model accepts additional fields of type array.*

## Structure

`OrderInformation20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails5`](../../doc/models/amount-details-5.md) | Optional | - | getAmountDetails(): ?AmountDetails5 | setAmountDetails(?AmountDetails5 amountDetails): void |
| `billTo` | [`?BillTo7`](../../doc/models/bill-to-7.md) | Optional | - | getBillTo(): ?BillTo7 | setBillTo(?BillTo7 billTo): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo7Builder;

$orderInformation20 = OrderInformation20Builder::init()
    ->amountDetails(
        AmountDetails5Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillTo7Builder::init()
            ->address1('address16')
            ->address2('address20')
            ->administrativeArea('administrativeArea4')
            ->buildingNumber('buildingNumber8')
            ->company('company8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

