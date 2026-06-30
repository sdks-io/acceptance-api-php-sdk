
# Watch List

*This model accepts additional fields of type array.*

## Structure

`WatchList`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `matches` | [`?(Match2[])`](../../doc/models/match.md) | Optional | - | getMatches(): ?array | setMatches(?array matches): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchListBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Match2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$watchList = WatchListBuilder::init()
    ->matches(
        [
            Match2Builder::init()
                ->addresses(
                    [
                        'addresses8'
                    ]
                )
                ->sanctionList('sanctionList4')
                ->aliases(
                    [
                        'aliases0',
                        'aliases1',
                        'aliases2'
                    ]
                )
                ->programs(
                    [
                        'programs3',
                        'programs4'
                    ]
                )
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Match2Builder::init()
                ->addresses(
                    [
                        'addresses8'
                    ]
                )
                ->sanctionList('sanctionList4')
                ->aliases(
                    [
                        'aliases0',
                        'aliases1',
                        'aliases2'
                    ]
                )
                ->programs(
                    [
                        'programs3',
                        'programs4'
                    ]
                )
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Match2Builder::init()
                ->addresses(
                    [
                        'addresses8'
                    ]
                )
                ->sanctionList('sanctionList4')
                ->aliases(
                    [
                        'aliases0',
                        'aliases1',
                        'aliases2'
                    ]
                )
                ->programs(
                    [
                        'programs3',
                        'programs4'
                    ]
                )
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

