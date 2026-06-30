
# Card Art

*This model accepts additional fields of type array.*

## Structure

`CardArt`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `foregroundColor` | `?string` | Optional, Read-only | Card foreground color. | getForegroundColor(): ?string | setForegroundColor(?string foregroundColor): void |
| `combinedAsset` | [`?CombinedAsset2`](../../doc/models/combined-asset-2.md) | Optional, Read-only | - | getCombinedAsset(): ?CombinedAsset2 | setCombinedAsset(?CombinedAsset2 combinedAsset): void |
| `brandLogoAsset` | [`?BrandLogoAsset2`](../../doc/models/brand-logo-asset-2.md) | Optional, Read-only | - | getBrandLogoAsset(): ?BrandLogoAsset2 | setBrandLogoAsset(?BrandLogoAsset2 brandLogoAsset): void |
| `issuerLogoAsset` | [`?IssuerLogoAsset2`](../../doc/models/issuer-logo-asset-2.md) | Optional, Read-only | - | getIssuerLogoAsset(): ?IssuerLogoAsset2 | setIssuerLogoAsset(?IssuerLogoAsset2 issuerLogoAsset): void |
| `iconAsset` | [`?IconAsset2`](../../doc/models/icon-asset-2.md) | Optional, Read-only | - | getIconAsset(): ?IconAsset2 | setIconAsset(?IconAsset2 iconAsset): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CardArtBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CombinedAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BrandLogoAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerLogoAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self24Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IconAsset2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self25Builder;

$cardArt = CardArtBuilder::init()
    ->foregroundColor('foregroundColor8')
    ->combinedAsset(
        CombinedAsset2Builder::init()
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
            ->build()
    )
    ->brandLogoAsset(
        BrandLogoAsset2Builder::init()
            ->id('id6')
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
            ->build()
    )
    ->issuerLogoAsset(
        IssuerLogoAsset2Builder::init()
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
            ->build()
    )
    ->iconAsset(
        IconAsset2Builder::init()
            ->id('id8')
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
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

