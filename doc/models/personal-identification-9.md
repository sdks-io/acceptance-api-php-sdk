
# Personal Identification 9

*This model accepts additional fields of type array.*

## Structure

`PersonalIdentification9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The value of the identification type.<br><br>**Constraints**: *Maximum Length*: `26` | getId(): ?string | setId(?string id): void |
| `type` | `?string` | Optional | The type of the identification.<br><br>Possible Values:<br><br>- driver license | getType(): ?string | setType(?string type): void |
| `issuedBy` | [`?IssuedBy`](../../doc/models/issued-by.md) | Optional | - | getIssuedBy(): ?IssuedBy | setIssuedBy(?IssuedBy issuedBy): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentification9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuedByBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$personalIdentification9 = PersonalIdentification9Builder::init()
    ->id('id4')
    ->type('type6')
    ->issuedBy(
        IssuedByBuilder::init()
            ->administrativeArea('administrativeArea4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

