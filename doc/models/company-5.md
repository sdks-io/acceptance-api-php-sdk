
# Company 5

*This model accepts additional fields of type array.*

## Structure

`Company5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the customer’s company.<br><br>**Constraints**: *Maximum Length*: `60` | getName(): ?string | setName(?string name): void |
| `address1` | `?string` | Optional | Payment card billing street address as it appears on the credit card issuer’s records.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Used for additional address information. For example: _Attention: Accounts Payable_<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `address3` | `?string` | Optional | Additional address information (third line of the billing address)<br><br>**Constraints**: *Maximum Length*: `60` | getAddress3(): ?string | setAddress3(?string address3): void |
| `address4` | `?string` | Optional | Additional address information (fourth line of the billing address)<br><br>**Constraints**: *Maximum Length*: `60` | getAddress4(): ?string | setAddress4(?string address4): void |
| `administrativeArea` | `?string` | Optional | State or province of the billing address. Use the [State, Province, and Territory Codes for the United States and Canada](<br><br>**Constraints**: *Maximum Length*: `20` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `buildingNumber` | `?string` | Optional | Building number in the street address.<br><br>**Constraints**: *Maximum Length*: `256` | getBuildingNumber(): ?string | setBuildingNumber(?string buildingNumber): void |
| `country` | `?string` | Optional | Payment card billing country. Use the two-character [ISO Standard Country Codes](<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `district` | `?string` | Optional | Customer’s neighborhood, community, or region (a barrio in Brazil) within the city or municipality<br><br>**Constraints**: *Maximum Length*: `50` | getDistrict(): ?string | setDistrict(?string district): void |
| `locality` | `?string` | Optional | Payment card billing city.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | Postal code for the billing address. The postal code must consist of 5 to 9 digits.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Company5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$company5 = Company5Builder::init()
    ->name('Visa Inc')
    ->address1('277 Park Avenue')
    ->address2('50th Floor')
    ->address3('Desk NY-50110')
    ->address4('address4')
    ->administrativeArea('NY')
    ->buildingNumber('buildingNumber')
    ->country('US')
    ->district('district')
    ->locality('New York')
    ->postalCode('10172')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

