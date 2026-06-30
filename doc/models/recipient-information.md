
# Recipient Information

*This model accepts additional fields of type array.*

## Structure

`RecipientInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountId` | `?string` | Optional | Identifier for the recipient’s account.<br>This field is applicable for AFT transactions.<br><br>**Constraints**: *Maximum Length*: `50` | getAccountId(): ?string | setAccountId(?string accountId): void |
| `accountType` | `?string` | Optional | Identifies the recipient’s account type.<br>This field is applicable for AFT transactions.<br><br>Valid values are:<br><br>- `00` for Other<br>- `01` for Routing Transit Number (RTN) + Bank Account Number (BAN)<br>- `02` for International Bank Account Number (IBAN)<br>- `03` for Card Account<br>- `06` for Bank Account Number (BAN) + Bank Identification Code (BIC), also known as a SWIFT code<br><br>**Constraints**: *Maximum Length*: `2` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `firstName` | `?string` | Optional | First name of the recipient.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `35` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `middleName` | `?string` | Optional | Middle name of the recipient.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `30` | getMiddleName(): ?string | setMiddleName(?string middleName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `35` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | The street address of the recipient<br>This field is applicable for AFT and OCT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `50` | getAddress1(): ?string | setAddress1(?string address1): void |
| `administrativeArea` | `?string` | Optional | The state or province of the recipient.<br>This field is applicable for AFT transactions when the recipient country is US or CA. Else it is optional.<br><br>Must be a two character value<br><br>**Constraints**: *Maximum Length*: `2` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Partial postal code for the recipient’s address. For example, if the postal code is **NN5 7SG**, the value for<br>this field should be the first part of the postal code: **NN5**. This field is a _pass-through_, which means that<br>Visa Acceptance does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | The country associated with the address of the recipient.<br>This field is applicable for AFT and OCT transactions.<br><br>Must be a two character ISO country code.<br>For example, see [ISO Country Code](<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `dateOfBirth` | `?string` | Optional | Recipient’s date of birth. **Format**: `YYYYMMDD`.<br><br>This field is a `pass-through`, which means that Visa Acceptance ensures that the value is eight numeric characters<br>but otherwise does not verify the value or modify it in any way before sending it to the processor. If the field<br>is not required for the transaction, Visa Acceptance does not forward it to the processor.<br><br>**Constraints**: *Maximum Length*: `8` | getDateOfBirth(): ?string | setDateOfBirth(?string dateOfBirth): void |
| `beneficiaryId` | `?string` | Optional | Only for e-wallets: ID, username, hash or anything uniquely identifying<br>the ultimate beneficiary.<br><br>**Constraints**: *Maximum Length*: `255` | getBeneficiaryId(): ?string | setBeneficiaryId(?string beneficiaryId): void |
| `beneficiaryName` | `?string` | Optional | Only for e-wallets: The ultimate beneficiary’s full name.<br><br>**Constraints**: *Maximum Length*: `255` | getBeneficiaryName(): ?string | setBeneficiaryName(?string beneficiaryName): void |
| `beneficiaryAddress` | `?string` | Optional | Only for e-wallets: The ultimate beneficiary’s street address (street,<br>zip code, city), excluding the country. Example: “Main street 1, 12345,<br>Barcelona<br><br>**Constraints**: *Maximum Length*: `255` | getBeneficiaryAddress(): ?string | setBeneficiaryAddress(?string beneficiaryAddress): void |
| `aliasName` | `?string` | Optional | Account owner alias name.<br><br>**Constraints**: *Maximum Length*: `50` | getAliasName(): ?string | setAliasName(?string aliasName): void |
| `nationality` | `?string` | Optional | Account Owner Nationality<br><br>**Constraints**: *Maximum Length*: `10` | getNationality(): ?string | setNationality(?string nationality): void |
| `countryOfBirth` | `?string` | Optional | Account Owner Country of Birth<br><br>**Constraints**: *Maximum Length*: `10` | getCountryOfBirth(): ?string | setCountryOfBirth(?string countryOfBirth): void |
| `occupation` | `?string` | Optional | Account Owner Occupation<br><br>**Constraints**: *Maximum Length*: `50` | getOccupation(): ?string | setOccupation(?string occupation): void |
| `email` | `?string` | Optional | Account Owner email address<br><br>**Constraints**: *Maximum Length*: `150` | getEmail(): ?string | setEmail(?string email): void |
| `locality` | `?string` | Optional | The city of the recipient.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported.<br>Special characters not in the standard ASCII character set are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `25` | getLocality(): ?string | setLocality(?string locality): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecipientInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recipientInformation = RecipientInformationBuilder::init()
    ->accountId('accountId0')
    ->accountType('accountType0')
    ->firstName('firstName4')
    ->middleName('middleName8')
    ->lastName('lastName4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

