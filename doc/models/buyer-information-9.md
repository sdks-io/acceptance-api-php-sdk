
# Buyer Information 9

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `gender` | `?string` | Optional | Customer's gender. Possible values are F (female), M (male),O (other).<br><br>**Constraints**: *Maximum Length*: `3` | getGender(): ?string | setGender(?string gender): void |
| `language` | `?string` | Optional | language setting of the user.<br>Supports 2-character language codes (e.g., en, fr) and 5-character locale values (e.g., en-US, fr-CA).<br><br>**Constraints**: *Maximum Length*: `5` | getLanguage(): ?string | setLanguage(?string language): void |
| `noteToSeller` | `?string` | Optional | Note to the recipient of the funds in this transaction<br><br>**Constraints**: *Maximum Length*: `255` | getNoteToSeller(): ?string | setNoteToSeller(?string noteToSeller): void |
| `personalIdentification` | [`?(PersonalIdentification2[])`](../../doc/models/personal-identification-2.md) | Optional | - | getPersonalIdentification(): ?array | setPersonalIdentification(?array personalIdentification): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PersonalIdentification2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation9 = BuyerInformation9Builder::init()
    ->dateOfBirth('dateOfBirth6')
    ->gender('gender4')
    ->language('language4')
    ->noteToSeller('noteToSeller6')
    ->personalIdentification(
        [
            PersonalIdentification2Builder::init()
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentification2Builder::init()
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PersonalIdentification2Builder::init()
                ->id('id8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

