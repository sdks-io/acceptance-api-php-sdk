
# Buyer Information 8

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `personalIdentification` | [`?(PersonalIdentification6[])`](../../doc/models/personal-identification-6.md) | Optional | - | getPersonalIdentification(): ?array | setPersonalIdentification(?array personalIdentification): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentification6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation8 = BuyerInformation8Builder::init()
    ->personalIdentification(
        [
            PersonalIdentification6Builder::init()
                ->type('type2')
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentification6Builder::init()
                ->type('type2')
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentification6Builder::init()
                ->type('type2')
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

