
# Order Information 19

*This model accepts additional fields of type array.*

## Structure

`OrderInformation19`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billTo` | [`?BillTo6`](../../doc/models/bill-to-6.md) | Optional | - | getBillTo(): ?BillTo6 | setBillTo(?BillTo6 billTo): void |
| `shipTo` | [`?ShipTo6`](../../doc/models/ship-to-6.md) | Optional | - | getShipTo(): ?ShipTo6 | setShipTo(?ShipTo6 shipTo): void |
| `amountDetails` | [`?AmountDetails22`](../../doc/models/amount-details-22.md) | Optional | - | getAmountDetails(): ?AmountDetails22 | setAmountDetails(?AmountDetails22 amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails22Builder;

$orderInformation19 = OrderInformation19Builder::init()
    ->billTo(
        BillTo6Builder::init()
            ->firstName('firstName4')
            ->lastName('lastName2')
            ->nameSuffix('nameSuffix8')
            ->address1('address16')
            ->address2('address20')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo6Builder::init()
            ->firstName('firstName0')
            ->lastName('lastName8')
            ->address1('address12')
            ->address2('address26')
            ->locality('locality4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->amountDetails(
        AmountDetails22Builder::init()
            ->refundBalance('refundBalance2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

