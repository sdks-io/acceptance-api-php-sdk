
# Ship to 7

*This model accepts additional fields of type array.*

## Structure

`ShipTo7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `100` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `100` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>**Constraints**: *Maximum Length*: `40` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address. Use the [State, Province, and Territory Codes for the United States and Canada]( (maximum length: 2)<br><br>**Constraints**: *Maximum Length*: `40` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>**Constraints**: *Maximum Length*: `20` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character [ISO Standard Country Codes.](<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo7 = ShipTo7Builder::init()
    ->firstName('firstName0')
    ->lastName('lastName8')
    ->address1('address12')
    ->address2('address26')
    ->locality('locality4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

