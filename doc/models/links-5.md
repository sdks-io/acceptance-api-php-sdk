
# Links 5

*This model accepts additional fields of type array.*

## Structure

`Links5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?MSelf`](../../doc/models/m-self.md) | Optional | - | getSelf(): ?MSelf | setSelf(?MSelf self): void |
| `void` | [`?Void2`](../../doc/models/void.md) | Optional | - | getVoid(): ?Void2 | setVoid(?Void2 void): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MSelfBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Void2Builder;

$links5 = Links5Builder::init()
    ->self(
        MSelfBuilder::init()
            ->href('href0')
            ->method('method8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->void(
        Void2Builder::init()
            ->href('href2')
            ->method('method6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

