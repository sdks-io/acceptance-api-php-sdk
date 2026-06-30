
# Electronic Verification Results 1

*This model accepts additional fields of type array.*

## Structure

`ElectronicVerificationResults1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `email` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s email address.<br><br>**Constraints**: *Maximum Length*: `1` | getEmail(): ?string | setEmail(?string email): void |
| `emailRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s email address.<br><br>**Constraints**: *Maximum Length*: `1` | getEmailRaw(): ?string | setEmailRaw(?string emailRaw): void |
| `name` | `?string` | Optional | #### Visa Platform Connect<br><br>Mapped Electronic Verification response code for the customer’s name.<br><br>Valid values :<br><br>'Y'   Yes, the data Matches<br>'N'   No Match<br>'O'   Partial Match<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `nameRaw` | `?string` | Optional | #### Visa Platform Connect<br><br>Raw Electronic Verification response code from the processor for the customer’s name.<br><br>Valid values :<br><br>'01'     Match<br>'50'     Partial Match<br>'99'     No Match<br><br>**Constraints**: *Maximum Length*: `30` | getNameRaw(): ?string | setNameRaw(?string nameRaw): void |
| `phoneNumber` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s phone number.<br><br>**Constraints**: *Maximum Length*: `1` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `phoneNumberRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s phone number.<br><br>**Constraints**: *Maximum Length*: `1` | getPhoneNumberRaw(): ?string | setPhoneNumberRaw(?string phoneNumberRaw): void |
| `street` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s street address.<br><br>**Constraints**: *Maximum Length*: `1` | getStreet(): ?string | setStreet(?string street): void |
| `streetRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s street address.<br><br>**Constraints**: *Maximum Length*: `1` | getStreetRaw(): ?string | setStreetRaw(?string streetRaw): void |
| `postalCode` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s postal code.<br><br>**Constraints**: *Maximum Length*: `1` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `postalCodeRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s postal code.<br><br>**Constraints**: *Maximum Length*: `1` | getPostalCodeRaw(): ?string | setPostalCodeRaw(?string postalCodeRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ElectronicVerificationResults1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$electronicVerificationResults1 = ElectronicVerificationResults1Builder::init()
    ->email('email6')
    ->emailRaw('emailRaw8')
    ->name('name0')
    ->nameRaw('nameRaw0')
    ->phoneNumber('phoneNumber0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

