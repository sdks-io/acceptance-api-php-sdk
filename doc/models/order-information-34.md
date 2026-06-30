
# Order Information 34

*This model accepts additional fields of type array.*

## Structure

`OrderInformation34`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails36`](../../doc/models/amount-details-36.md) | Optional | - | getAmountDetails(): ?AmountDetails36 | setAmountDetails(?AmountDetails36 amountDetails): void |
| `billTo` | [`?BillTo57`](../../doc/models/bill-to-57.md) | Optional | - | getBillTo(): ?BillTo57 | setBillTo(?BillTo57 billTo): void |
| `shipTo` | [`?ShipTo26`](../../doc/models/ship-to-26.md) | Optional | - | getShipTo(): ?ShipTo26 | setShipTo(?ShipTo26 shipTo): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation34Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails36Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo57Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo26Builder;

$orderInformation34 = OrderInformation34Builder::init()
    ->amountDetails(
        AmountDetails36Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillTo57Builder::init()
            ->address1('address16')
            ->address2('address20')
            ->address3('address38')
            ->address4('address42')
            ->administrativeArea('administrativeArea4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo26Builder::init()
            ->address1('address12')
            ->address2('address26')
            ->address3('address34')
            ->address4('address48')
            ->administrativeArea('administrativeArea0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

