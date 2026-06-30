
# Ship to 1

*This model accepts additional fields of type array.*

## Structure

`ShipTo1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstname` | `?string` | Optional | First name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstname(): ?string | setFirstname(?string firstname): void |
| `lastname` | `?string` | Optional | Last name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getLastname(): ?string | setLastname(?string lastname): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `100` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `100` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of shipping address. This is a State, Province, and Territory Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `40` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code of the shipping address. Consists of 5 to 9 digits.<br><br>**Constraints**: *Maximum Length*: `20` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country of shipping address. This is a two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `phoneNumber` | `?string` | Optional | Phone number of the recipient.<br><br>**Constraints**: *Maximum Length*: `20` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo1 = ShipTo1Builder::init()
    ->firstname('firstname0')
    ->lastname('lastname6')
    ->address1('address10')
    ->address2('address24')
    ->locality('locality2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

