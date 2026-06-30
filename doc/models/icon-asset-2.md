
# Icon Asset 2

*This model accepts additional fields of type array.*

## Structure

`IconAsset2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the asset | getId(): ?string | setId(?string id): void |
| `links` | [`?Links26`](../../doc/models/links-26.md) | Optional, Read-only | - | getLinks(): ?Links26 | setLinks(?Links26 links): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IconAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self25Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$iconAsset2 = IconAsset2Builder::init()
    ->id('id6')
    ->links(
        Links26Builder::init()
            ->self(
                Self25Builder::init()
                    ->href('href0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

