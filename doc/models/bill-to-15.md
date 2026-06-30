
# Bill to 15

*This model accepts additional fields of type array.*

## Structure

`BillTo15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | Customer’s first name. This name must be the same as the name on the card.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Customer’s last name. This name must be the same as the name on the card.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `company` | `?string` | Optional | Name of the customer’s company.<br><br>**Constraints**: *Maximum Length*: `60` | getCompany(): ?string | setCompany(?string company): void |
| `address1` | `?string` | Optional | Payment card billing street address as it appears on the credit card issuer’s records.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Additional address information.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | Payment card billing city.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the billing address. Use the State, Province, and Territory Codes for the United States<br>and Canada.<br><br>**Constraints**: *Maximum Length*: `20` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the billing address. The postal code must consist of 5 to 9 digits.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>**Example** `12345-6789`<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>**Example** `A1B 2C3`<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Payment card billing country. Use the two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `email` | `?string` | Optional | Customer's email address, including the full domain name.<br><br>**Constraints**: *Maximum Length*: `255` | getEmail(): ?string | setEmail(?string email): void |
| `phoneNumber` | `?string` | Optional | Customer’s phone number.<br><br>**Constraints**: *Maximum Length*: `15` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo15 = BillTo15Builder::init()
    ->firstName('firstName8')
    ->lastName('lastName0')
    ->company('company4')
    ->address1('address14')
    ->address2('address28')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

