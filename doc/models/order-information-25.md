
# Order Information 25

*This model accepts additional fields of type array.*

## Structure

`OrderInformation25`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billTo` | [`?BillTo11`](../../doc/models/bill-to-11.md) | Optional | - | getBillTo(): ?BillTo11 | setBillTo(?BillTo11 billTo): void |
| `shipTo` | [`?ShipTo8`](../../doc/models/ship-to-8.md) | Optional | - | getShipTo(): ?ShipTo8 | setShipTo(?ShipTo8 shipTo): void |
| `amountDetails` | [`?AmountDetails27`](../../doc/models/amount-details-27.md) | Optional | - | getAmountDetails(): ?AmountDetails27 | setAmountDetails(?AmountDetails27 amountDetails): void |
| `shippingDetails` | [`?ShippingDetails5`](../../doc/models/shipping-details-5.md) | Optional | - | getShippingDetails(): ?ShippingDetails5 | setShippingDetails(?ShippingDetails5 shippingDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingDetails5Builder;

$orderInformation25 = OrderInformation25Builder::init()
    ->billTo(
        BillTo11Builder::init()
            ->title('title4')
            ->firstName('firstName4')
            ->middleName('middleName6')
            ->lastName('lastName2')
            ->nameSuffix('nameSuffix8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo8Builder::init()
            ->method('method8')
            ->firstName('firstName0')
            ->lastName('lastName8')
            ->address1('address12')
            ->address2('address26')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->amountDetails(
        AmountDetails27Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingDetails(
        ShippingDetails5Builder::init()
            ->shippingMethod('shippingMethod6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

