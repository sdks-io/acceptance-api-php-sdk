
# Electronic Verification Results

*This model accepts additional fields of type array.*

## Structure

`ElectronicVerificationResults`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s name.<br><br>**Constraints**: *Maximum Length*: `1` | getCode(): ?string | setCode(?string code): void |
| `codeRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s last name<br><br>**Constraints**: *Maximum Length*: `1` | getCodeRaw(): ?string | setCodeRaw(?string codeRaw): void |
| `email` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s email address.<br><br>**Constraints**: *Maximum Length*: `1` | getEmail(): ?string | setEmail(?string email): void |
| `emailRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s email address.<br><br>**Constraints**: *Maximum Length*: `1` | getEmailRaw(): ?string | setEmailRaw(?string emailRaw): void |
| `phoneNumber` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s phone number.<br><br>**Constraints**: *Maximum Length*: `1` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `phoneNumberRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s phone number.<br><br>**Constraints**: *Maximum Length*: `1` | getPhoneNumberRaw(): ?string | setPhoneNumberRaw(?string phoneNumberRaw): void |
| `postalCode` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s postal code.<br><br>**Constraints**: *Maximum Length*: `1` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `postalCodeRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s postal code.<br><br>**Constraints**: *Maximum Length*: `1` | getPostalCodeRaw(): ?string | setPostalCodeRaw(?string postalCodeRaw): void |
| `street` | `?string` | Optional | Mapped Electronic Verification response code for the customer’s street address.<br><br>**Constraints**: *Maximum Length*: `1` | getStreet(): ?string | setStreet(?string street): void |
| `streetRaw` | `?string` | Optional | Raw Electronic Verification response code from the processor for the customer’s street address.<br><br>**Constraints**: *Maximum Length*: `1` | getStreetRaw(): ?string | setStreetRaw(?string streetRaw): void |
| `name` | `?string` | Optional | #### Visa Platform Connect<br><br>Mapped Electronic Verification response code for the customer’s name.<br><br>Valid values :<br><br>'Y'   Yes, the data Matches<br>'N'   No Match<br>'O'   Partial Match<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `nameRaw` | `?string` | Optional | #### Visa Platform Connect<br><br>Raw Electronic Verification response code from the processor for the customer’s name.<br><br>Valid values :<br><br>'01'     Match<br>'50'     Partial Match<br>'99'     No Match<br><br>**Constraints**: *Maximum Length*: `30` | getNameRaw(): ?string | setNameRaw(?string nameRaw): void |
| `firstNameRaw` | `?string` | Optional | #### Visa Platform Connect<br><br>Raw electronic verification response code from the processor for the customer’s first name.<br><br>Valid values :<br><br>'01'     Match<br>'50'     Partial Match<br>'99'     No Match<br><br>**Constraints**: *Maximum Length*: `2` | getFirstNameRaw(): ?string | setFirstNameRaw(?string firstNameRaw): void |
| `firstName` | `?string` | Optional | #### Visa Platform Connect<br><br>Mapped electronic verification response code from the processor for the customer’s first name.<br><br>Valid values :<br><br>'Y'   Yes, the data Matches<br>'N'   No Match<br>'O'   Partial Match<br><br>**Constraints**: *Maximum Length*: `1` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `middleNameRaw` | `?string` | Optional | #### Visa Platform Connect<br><br>Raw electronic verification response code from the processor for the customer’s middle name.<br><br>Valid values :<br><br>'01'     Match<br>'50'     Partial Match<br>'99'     No Match<br><br>**Constraints**: *Maximum Length*: `2` | getMiddleNameRaw(): ?string | setMiddleNameRaw(?string middleNameRaw): void |
| `middleName` | `?string` | Optional | #### Visa Platform Connect<br><br>Mapped electronic verification response code from the processor for the customer’s middle name.<br><br>Valid values :<br><br>'Y'   Yes, the data Matches<br>'N'   No Match<br>'O'   Partial Match<br><br>**Constraints**: *Maximum Length*: `1` | getMiddleName(): ?string | setMiddleName(?string middleName): void |
| `lastNameRaw` | `?string` | Optional | #### Visa Platform Connect<br><br>Raw electronic verification response code from the processor for the customer’s last name.<br><br>Valid values :<br><br>'01'     Match<br>'50'     Partial Match<br>'99'     No Match<br><br>**Constraints**: *Maximum Length*: `2` | getLastNameRaw(): ?string | setLastNameRaw(?string lastNameRaw): void |
| `lastName` | `?string` | Optional | #### Visa Platform Connect<br><br>Mapped electronic verification response code from the processor for the customer’s last name.<br><br>Valid values :<br><br>'Y'   Yes, the data Matches<br>'N'   No Match<br>'O'   Partial Match<br><br>**Constraints**: *Maximum Length*: `1` | getLastName(): ?string | setLastName(?string lastName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ElectronicVerificationResultsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$electronicVerificationResults = ElectronicVerificationResultsBuilder::init()
    ->code('code8')
    ->codeRaw('codeRaw4')
    ->email('email6')
    ->emailRaw('emailRaw8')
    ->phoneNumber('phoneNumber0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

