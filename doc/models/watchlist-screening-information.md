
# Watchlist Screening Information

*This model accepts additional fields of type array.*

## Structure

`WatchlistScreeningInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addressOperator` | `?string` | Optional | Parts of the customer’s information that must match with an entry in the DPL (denied parties list)<br>before a match occurs. This field can contain one of the following values:<br><br>- AND: (default) The customer’s name or company and the customer’s address must appear in the database.<br>- OR: The customer’s name must appear in the database.<br>- IGNORE: You want the service to detect a match only of the customer’s name or company but not of the address. | getAddressOperator(): ?string | setAddressOperator(?string addressOperator): void |
| `weights` | [`?Weights`](../../doc/models/weights.md) | Optional | - | getWeights(): ?Weights | setWeights(?Weights weights): void |
| `sanctionLists` | `?(string[])` | Optional | Use this field to specify which list(s) you want checked with the request.<br>The reply will include the list name as well as the response data.<br>To check against multiple lists, enter multiple list codes separated by a caret (^).<br>For more information, see "Restricted and Denied Parties List," page 68.<br><br>**Constraints**: *Maximum Length*: `255` | getSanctionLists(): ?array | setSanctionLists(?array sanctionLists): void |
| `proceedOnMatch` | `?bool` | Optional | Indicates whether the transaction should proceed if there is a match.<br>Possible values:<br><br>- `true`: Transaction proceeds even when match is found in the Denied Parties List. The match is noted in the response.<br>- `false`: Normal watchlist screening behavior occurs. (Transaction stops if a match to DPL occurs. Transaction proceeds if no match.) | getProceedOnMatch(): ?bool | setProceedOnMatch(?bool proceedOnMatch): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\WatchlistScreeningInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\WeightsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$watchlistScreeningInformation = WatchlistScreeningInformationBuilder::init()
    ->addressOperator('addressOperator0')
    ->weights(
        WeightsBuilder::init()
            ->address('address2')
            ->company('company4')
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->sanctionLists(
        [
            'sanctionLists1',
            'sanctionLists2'
        ]
    )
    ->proceedOnMatch(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

