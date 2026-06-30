
# Bill to 9

*This model accepts additional fields of type array.*

## Structure

`BillTo9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | Customer’s first name.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Customer’s last name.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the billing street address.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Additional address information.<br>Example: Attention - Accounts Payable<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the billing address.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State of the billing address in the U.S.<br><br>**Constraints**: *Maximum Length*: `2` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the billing address. The postal code must consist of 5 to 9 digits.<br>A 9-digit postal code must follow this format: [5 digits][dash][4 digits]<br><br>Example: 12345-6789"<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Billing country. Use the two character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `email` | `?string` | Optional | Customer’s email address, including the full<br>domain name.<br><br>**Constraints**: *Maximum Length*: `256` | getEmail(): ?string | setEmail(?string email): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo9 = BillTo9Builder::init()
    ->firstName('firstName2')
    ->lastName('lastName6')
    ->address1('address10')
    ->address2('address24')
    ->locality('locality2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

