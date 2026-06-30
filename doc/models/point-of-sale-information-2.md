
# Point of Sale Information 2

*This model accepts additional fields of type array.*

## Structure

`PointOfSaleInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `emv` | [`?Emv2`](../../doc/models/emv-2.md) | Optional | - | getEmv(): ?Emv2 | setEmv(?Emv2 emv): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PointOfSaleInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Emv2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$pointOfSaleInformation2 = PointOfSaleInformation2Builder::init()
    ->emv(
        Emv2Builder::init()
            ->tags('tags4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

