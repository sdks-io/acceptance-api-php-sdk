
# Bill to 3

*This model accepts additional fields of type array.*

## Structure

`BillTo3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `address1` | `?string` | Optional | Payment card billing street address as it appears on the credit card issuer’s records.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Additional address information.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | Payment card billing city.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the billing address. Use the State, Province, and Territory Codes for the United States<br>and Canada.<br><br>**Constraints**: *Maximum Length*: `20` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the billing address. The postal code must consist of 5 to 9 digits.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>**Example** `12345-6789`<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>**Example** `A1B 2C3`<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Payment card billing country. Use the two-character ISO Standard Country Codes.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$billTo3 = BillTo3Builder::init()
    ->address1('address18')
    ->address2('address22')
    ->locality('locality0')
    ->administrativeArea('administrativeArea6')
    ->postalCode('postalCode2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

