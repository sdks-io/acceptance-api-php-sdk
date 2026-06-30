
# Links 25

*This model accepts additional fields of type array.*

## Structure

`Links25`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self24`](../../doc/models/self-24.md) | Optional, Read-only | - | getSelf(): ?Self24 | setSelf(?Self24 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self24Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links25 = Links25Builder::init()
    ->self(
        Self24Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

