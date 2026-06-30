
# Metadata 2

Metadata associated with the tokenized card.

*This model accepts additional fields of type array.*

## Structure

`Metadata2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cardArt` | [`?CardArt`](../../doc/models/card-art.md) | Optional, Read-only | - | getCardArt(): ?CardArt | setCardArt(?CardArt cardArt): void |
| `issuer` | [`?Issuer1`](../../doc/models/issuer-1.md) | Optional, Read-only | - | getIssuer(): ?Issuer1 | setIssuer(?Issuer1 issuer): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata2Builder;
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
use VisaAcceptanceMergedSpecLib\Models\Builders\Issuer1Builder;

$metadata2 = Metadata2Builder::init()
    ->cardArt(
        CardArtBuilder::init()
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
            ->build()
    )
    ->issuer(
        Issuer1Builder::init()
            ->name('name0')
            ->shortDescription('shortDescription6')
            ->longDescription('longDescription0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

