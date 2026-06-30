
# Get Card Art Asset Response

Represents the Card Art Asset associated to the Network Token.

*This model accepts additional fields of type array.*

## Structure

`GetCardArtAssetResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Card Art Asset. | getId(): ?string | setId(?string id): void |
| `type` | `?string` | Optional | The type of Card Art Asset. | getType(): ?string | setType(?string type): void |
| `provider` | `?string` | Optional | The provider of the Card Art Asset. | getProvider(): ?string | setProvider(?string provider): void |
| `content` | [`?(Content[])`](../../doc/models/content.md) | Optional | Array of content objects representing the Card Art Asset. | getContent(): ?array | setContent(?array content): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\GetCardArtAssetResponseBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ContentBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$getCardArtAssetResponse = GetCardArtAssetResponseBuilder::init()
    ->id('84cfb836a0000859be62c766bdc9e510')
    ->type('cardArtCombined')
    ->provider('vts')
    ->content(
        [
            ContentBuilder::init()
                ->type('type6')
                ->data('data4')
                ->width(248)
                ->height(156)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            ContentBuilder::init()
                ->type('type6')
                ->data('data4')
                ->width(248)
                ->height(156)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

