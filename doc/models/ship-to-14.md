
# Ship to 14

*This model accepts additional fields of type array.*

## Structure

`ShipTo14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `company` | `?string` | Optional | Company associated with the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getCompany(): ?string | setCompany(?string company): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address. Use 2 character the State,<br>Province, and Territory Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `20` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>Example A1B 2C3<br><br>**American Express Direct**\<br>Before sending the postal code to the processor, all nonalphanumeric characters are removed and, if the<br>remaining value is longer than nine characters, truncates the value starting from the right side.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `email` | `?string` | Optional | Email associated with the shipping address.<br><br>**Constraints**: *Maximum Length*: `320` | getEmail(): ?string | setEmail(?string email): void |
| `phoneNumber` | `?string` | Optional | Phone number associated with the shipping address.<br><br>**Constraints**: *Maximum Length*: `15` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo14 = ShipTo14Builder::init()
    ->firstName('firstName2')
    ->lastName('lastName6')
    ->company('company2')
    ->address1('address10')
    ->address2('address24')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

