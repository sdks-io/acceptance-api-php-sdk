
# Links 23

*This model accepts additional fields of type array.*

## Structure

`Links23`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self22`](../../doc/models/self-22.md) | Optional, Read-only | - | getSelf(): ?Self22 | setSelf(?Self22 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links23 = Links23Builder::init()
    ->self(
        Self22Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

