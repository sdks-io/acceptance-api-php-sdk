
# Buyer Information 7

*This model accepts additional fields of type array.*

## Structure

`BuyerInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `gender` | `?string` | Optional | Customer's gender. Possible values are F (female), M (male), O (other).<br><br>**Constraints**: *Maximum Length*: `1` | getGender(): ?string | setGender(?string gender): void |
| `language` | `?string` | Optional | language setting of the user<br><br>**Constraints**: *Maximum Length*: `5` | getLanguage(): ?string | setLanguage(?string language): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$buyerInformation7 = BuyerInformation7Builder::init()
    ->dateOfBirth('dateOfBirth8')
    ->gender('gender0')
    ->language('language8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

