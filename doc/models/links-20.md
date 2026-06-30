
# Links 20

*This model accepts additional fields of type array.*

## Structure

`Links20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self19`](../../doc/models/self-19.md) | Optional, Read-only | - | getSelf(): ?Self19 | setSelf(?Self19 self): void |
| `customer` | [`?Self18`](../../doc/models/self-18.md) | Optional, Read-only | - | getCustomer(): ?Self18 | setCustomer(?Self18 customer): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;

$links20 = Links20Builder::init()
    ->self(
        Self19Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        Self18Builder::init()
            ->href('href2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

