
# Brand Logo Asset 2

*This model accepts additional fields of type array.*

## Structure

`BrandLogoAsset2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the asset | getId(): ?string | setId(?string id): void |
| `links` | [`?Links24`](../../doc/models/links-24.md) | Optional, Read-only | - | getLinks(): ?Links24 | setLinks(?Links24 links): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BrandLogoAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self23Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$brandLogoAsset2 = BrandLogoAsset2Builder::init()
    ->id('id2')
    ->links(
        Links24Builder::init()
            ->self(
                Self23Builder::init()
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

