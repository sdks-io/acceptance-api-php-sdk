
# Links 1

*This model accepts additional fields of type array.*

## Structure

`Links1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?MSelf`](../../doc/models/m-self.md) | Optional | - | getSelf(): ?MSelf | setSelf(?MSelf self): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MSelfBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$links1 = Links1Builder::init()
    ->self(
        MSelfBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

