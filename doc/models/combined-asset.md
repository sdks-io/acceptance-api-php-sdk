
# Combined Asset

Combined card art asset associated with the tokenized card.

*This model accepts additional fields of type array.*

## Structure

`CombinedAsset`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the asset | getId(): ?string | setId(?string id): void |
| `links` | [`?Links23`](../../doc/models/links-23.md) | Optional, Read-only | - | getLinks(): ?Links23 | setLinks(?Links23 links): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CombinedAssetBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$combinedAsset = CombinedAssetBuilder::init()
    ->id('id2')
    ->links(
        Links23Builder::init()
            ->self(
                Self22Builder::init()
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

