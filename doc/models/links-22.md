
# Links 22

*This model accepts additional fields of type array.*

## Structure

`Links22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self21`](../../doc/models/self-21.md) | Optional, Read-only | - | getSelf(): ?Self21 | setSelf(?Self21 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links22Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self21Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links22 = Links22Builder::init()
    ->self(
        Self21Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

