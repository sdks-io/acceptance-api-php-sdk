
# Links 26

*This model accepts additional fields of type array.*

## Structure

`Links26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self25`](../../doc/models/self-25.md) | Optional, Read-only | - | getSelf(): ?Self25 | setSelf(?Self25 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self25Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links26 = Links26Builder::init()
    ->self(
        Self25Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

