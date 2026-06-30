
# Order Information 22

*This model accepts additional fields of type array.*

## Structure

`OrderInformation22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billTo` | [`?BillTo9`](../../doc/models/bill-to-9.md) | Optional | - | getBillTo(): ?BillTo9 | setBillTo(?BillTo9 billTo): void |
| `shipTo` | [`?ShipTo7`](../../doc/models/ship-to-7.md) | Optional | - | getShipTo(): ?ShipTo7 | setShipTo(?ShipTo7 shipTo): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation22Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo7Builder;

$orderInformation22 = OrderInformation22Builder::init()
    ->billTo(
        BillTo9Builder::init()
            ->firstName('firstName4')
            ->lastName('lastName2')
            ->address1('address16')
            ->address2('address20')
            ->locality('locality8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo7Builder::init()
            ->firstName('firstName0')
            ->lastName('lastName8')
            ->address1('address12')
            ->address2('address26')
            ->locality('locality4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

