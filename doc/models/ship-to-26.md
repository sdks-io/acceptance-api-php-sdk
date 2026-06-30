
# Ship to 26

*This model accepts additional fields of type array.*

## Structure

`ShipTo26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `address3` | `?string` | Optional | Third line of the shipping address. | getAddress3(): ?string | setAddress3(?string address3): void |
| `address4` | `?string` | Optional | Fourth line of the shipping address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress4(): ?string | setAddress4(?string address4): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address.<br><br>Use the [State, Province, and Territory Codes for the United States and Canada](<br><br>**Constraints**: *Maximum Length*: `2` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `buildingNumber` | `?string` | Optional | Building number in the street address.<br><br>**Constraints**: *Maximum Length*: `15` | getBuildingNumber(): ?string | setBuildingNumber(?string buildingNumber): void |
| `country` | `?string` | Optional | Country of the shipping address.<br><br>Use the two-character [ISO Standard Country Codes.]( | getCountry(): ?string | setCountry(?string country): void |
| `district` | `?string` | Optional | Neighborhood, community, or region within a city or municipality.<br><br>**Constraints**: *Maximum Length*: `50` | getDistrict(): ?string | setDistrict(?string district): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `firstName` | `?string` | Optional | First name of the recipient<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo26 = ShipTo26Builder::init()
    ->address1('Visa Acceptance')
    ->address2('Victoria House')
    ->address3('15-17 Gloucester Street')
    ->address4('string')
    ->administrativeArea('CA')
    ->buildingNumber('string')
    ->country('GB')
    ->district('string')
    ->locality('Belfast')
    ->postalCode('BT1 4LS')
    ->firstName('John')
    ->lastName('Doe')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

