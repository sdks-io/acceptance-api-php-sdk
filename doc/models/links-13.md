
# Links 13

*This model accepts additional fields of type array.*

## Structure

`Links13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self13`](../../doc/models/self-13.md) | Optional | - | getSelf(): ?Self13 | setSelf(?Self13 self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links13 = Links13Builder::init()
    ->self(
        Self13Builder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

