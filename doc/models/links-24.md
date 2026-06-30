
# Links 24

*This model accepts additional fields of type array.*

## Structure

`Links24`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self23`](../../doc/models/self-23.md) | Optional, Read-only | - | getSelf(): ?Self23 | setSelf(?Self23 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self23Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links24 = Links24Builder::init()
    ->self(
        Self23Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

