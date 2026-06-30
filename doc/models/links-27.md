
# Links 27

*This model accepts additional fields of type array.*

## Structure

`Links27`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `self` | [`?Self26`](../../doc/models/self-26.md) | Optional, Read-only | - | getSelf(): ?Self26 | setSelf(?Self26 self): void |
| `customer` | [`?Customer15`](../../doc/models/customer-15.md) | Optional, Read-only | - | getCustomer(): ?Customer15 | setCustomer(?Customer15 customer): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Links27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer15Builder;

$links27 = Links27Builder::init()
    ->self(
        Self26Builder::init()
            ->href('href0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        Customer15Builder::init()
            ->href('href2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

