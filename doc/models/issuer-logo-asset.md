
# Issuer Logo Asset

Issuer logo card art asset associated with the tokenized card.

*This model accepts additional fields of type array.*

## Structure

`IssuerLogoAsset`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the asset | getId(): ?string | setId(?string id): void |
| `links` | [`?Links25`](../../doc/models/links-25.md) | Optional, Read-only | - | getLinks(): ?Links25 | setLinks(?Links25 links): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerLogoAssetBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self24Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerLogoAsset = IssuerLogoAssetBuilder::init()
    ->id('id4')
    ->links(
        Links25Builder::init()
            ->self(
                Self24Builder::init()
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

