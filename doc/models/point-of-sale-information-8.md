
# Point of Sale Information 8

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `emv` | [`?Emv6`](../../doc/models/emv-6.md) | Optional | - | getEmv(): ?Emv6 | setEmv(?Emv6 emv): void |
| `terminalCategory` | `?string` | Optional | Indicates the type of terminal.<br><br>Possible values:<br><br>- `AFD`: Automated Fuel Dispenser<br><br>**Constraints**: *Maximum Length*: `3` | getTerminalCategory(): ?string | setTerminalCategory(?string terminalCategory): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation8 = PointOfSaleInformation8Builder::init()
    ->emv(
        Emv6Builder::init()
            ->tags('tags4')
            ->fallback(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->terminalCategory('terminalCategory0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

