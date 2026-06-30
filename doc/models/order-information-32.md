
# Order Information 32

*This model accepts additional fields of type array.*

## Structure

`OrderInformation32`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `shipTo` | [`?ShipTo13`](../../doc/models/ship-to-13.md) | Optional | - | getShipTo(): ?ShipTo13 | setShipTo(?ShipTo13 shipTo): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation32Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orderInformation32 = OrderInformation32Builder::init()
    ->shipTo(
        ShipTo13Builder::init()
            ->firstName('firstName0')
            ->lastName('lastName8')
            ->address1('address12')
            ->address2('address26')
            ->administrativeArea('administrativeArea0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

