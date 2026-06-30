
# Watchlist Screening Information 1

*This model accepts additional fields of type array.*

## Structure

`WatchlistScreeningInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ipCountryConfidence` | `?int` | Optional | Likelihood that the country associated with the customer’s IP address was identified correctly.<br>Returns a value from 1–100, where 100 indicates the highest likelihood.<br>If the country cannot be determined, the value is –1.<br><br>**Constraints**: `>= -1`, `<= 100` | getIpCountryConfidence(): ?int | setIpCountryConfidence(?int ipCountryConfidence): void |
| `infoCodes` | `?(string[])` | Optional | Returned when the Denied Parties List check (first two codes) or the export service (all others) would have<br>declined the transaction. This field can contain one or more of these values:<br><br>- `MATCH-DPC`: Denied Parties List match.<br>- `UNV-DPC`: Denied Parties List unavailable.<br>- `MATCH-BCO`: Billing country restricted.<br>- `MATCH-EMCO`: Email country restricted.<br>- `MATCH-HCO`: Host name country restricted.<br>- `MATCH-IPCO`: IP country restricted.<br>- `MATCH-SCO`: Shipping country restricted.<br><br>**Constraints**: *Maximum Length*: `255` | getInfoCodes(): ?array | setInfoCodes(?array infoCodes): void |
| `watchList` | [`?WatchList`](../../doc/models/watch-list.md) | Optional | - | getWatchList(): ?WatchList | setWatchList(?WatchList watchList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchlistScreeningInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchListBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Match2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$watchlistScreeningInformation1 = WatchlistScreeningInformation1Builder::init()
    ->ipCountryConfidence(54)
    ->infoCodes(
        [
            'infoCodes0',
            'infoCodes1'
        ]
    )
    ->watchList(
        WatchListBuilder::init()
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
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

