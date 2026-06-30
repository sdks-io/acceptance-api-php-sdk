
# Match

*This model accepts additional fields of type array.*

## Structure

`Match`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `addresses` | `?(string[])` | Optional | Address found on the list specified in export_matchN_list<br>for the entity (name and address) in the request.<br><br>**Constraints**: *Maximum Length*: `255` | getAddresses(): ?array | setAddresses(?array addresses): void |
| `sanctionList` | `?string` | Optional | List on which the first Denied Parties List check match appears.<br>For a list of codes, see "Denied Parties List Check Codes," page 56.<br><br>**Constraints**: *Maximum Length*: `255` | getSanctionList(): ?string | setSanctionList(?string sanctionList): void |
| `aliases` | `?(string[])` | Optional | Name found on the list specified in export_matchN_list for the entity (name and address) in the request.<br><br>**Constraints**: *Maximum Length*: `255` | getAliases(): ?array | setAliases(?array aliases): void |
| `programs` | `?(string[])` | Optional | Sub-lists matched by the order data. List members are separated by carets (^).<br><br>**Constraints**: *Maximum Length*: `255` | getPrograms(): ?array | setPrograms(?array programs): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Match2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$match = Match2Builder::init()
    ->addresses(
        [
            'addresses6',
            'addresses7',
            'addresses8'
        ]
    )
    ->sanctionList('sanctionList2')
    ->aliases(
        [
            'aliases2'
        ]
    )
    ->programs(
        [
            'programs1'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

