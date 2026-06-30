
# Ship to 8

*This model accepts additional fields of type array.*

## Structure

`ShipTo8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | `?string` | Optional | shipping method for the product.<br>Possible values are:<br><br>- `sameday`<br>- `oneday`<br>- `twoday`<br>- `threeday`<br>- `lowcost`<br>- `pickup`<br>- `other`<br>- `none`<br><br>**Constraints**: *Maximum Length*: `225` | getMethod(): ?string | setMethod(?string method): void |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `100` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address<br><br>**Constraints**: *Maximum Length*: `100` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | Postal code of shipping address. Consists of 5 to 9 digits.<br><br>**Constraints**: *Maximum Length*: `20` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `administrativeArea` | `?string` | Optional | State or province of shipping address. This is a State, Province, and Territory Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `40` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `country` | `?string` | Optional | Country of shipping address. This is a two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `phoneNumber` | `?string` | Optional | Phone number of shipping address.<br><br>**Constraints**: *Maximum Length*: `20` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo8 = ShipTo8Builder::init()
    ->method('method2')
    ->firstName('firstName0')
    ->lastName('lastName8')
    ->address1('address12')
    ->address2('address26')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

