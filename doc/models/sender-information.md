
# Sender Information

*This model accepts additional fields of type array.*

## Structure

`SenderInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the sender.<br>This field is applicable for AFT and OCT transactions.<br><br>Only alpha numeric values are supported.Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to the processor.<br><br>**Constraints**: *Maximum Length*: `30` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `middleName` | `?string` | Optional | Middle name of the sender.<br>This field is applicable for AFT and OCT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `30` | getMiddleName(): ?string | setMiddleName(?string middleName): void |
| `lastName` | `?string` | Optional | Last name of the sender.<br>This field is applicable for AFT and OCT transactions.<br><br>Only alpha numeric values are supported. Special characters not in the standard ASCII character set, are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `35` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | The street address of the sender.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported.<br>Special characters not in the standard ASCII character set are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `35` | getAddress1(): ?string | setAddress1(?string address1): void |
| `locality` | `?string` | Optional | The city or locality of the sender.<br>This field is applicable for AFT transactions.<br><br>Only alpha numeric values are supported.<br>Special characters not in the standard ASCII character set are not supported and will be stripped before being sent to sent to the processor.<br><br>**Constraints**: *Maximum Length*: `25` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | The state or province of the sender.<br>This field is applicable for AFT transactions when the sender country is US or CA. Else it is optional.<br><br>Must be a two character value<br><br>**Constraints**: *Maximum Length*: `2` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `countryCode` | `?string` | Optional | The country associated with the address of the sender.<br>This field is applicable for AFT transactions.<br><br>Must be a two character ISO country code.<br>For example, see [ISO Country Code](<br><br>**Constraints**: *Maximum Length*: `2` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `aliasName` | `?string` | Optional | Sender's alias name.<br><br>**Constraints**: *Maximum Length*: `50` | getAliasName(): ?string | setAliasName(?string aliasName): void |
| `referenceNumber` | `?string` | Optional | This field is applicable for AFT transactions.<br><br>Contains a transaction reference number provided by the Merchant. Only alpha numeric values are supported.<br><br>**Constraints**: *Maximum Length*: `19` | getReferenceNumber(): ?string | setReferenceNumber(?string referenceNumber): void |
| `account` | [`?Account1`](../../doc/models/account-1.md) | Optional | - | getAccount(): ?Account1 | setAccount(?Account1 account): void |
| `postalCode` | `?string` | Optional | Postal code of sender.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\SenderInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$senderInformation = SenderInformationBuilder::init()
    ->firstName('firstName2')
    ->middleName('middleName4')
    ->lastName('lastName0')
    ->address1('address14')
    ->locality('locality6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

