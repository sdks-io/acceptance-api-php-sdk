
# Ship to 13

*This model accepts additional fields of type array.*

## Structure

`ShipTo13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>Optional field.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address. Use the [State, Province, and Territory Codes for the United States and Canada]( (maximum length: 2)<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S.<br>or Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S. or<br>Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>Required field for authorization if any shipping address information is included in the request and<br>shipping to the U.S. or Canada; otherwise, optional.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>Example A1B 2C3<br><br>#### American Express Direct<br><br>Before sending the postal code to the processor, all nonalphanumeric characters are removed and, if the<br>remaining value is longer than nine characters, the value is truncated starting from the right side.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `32` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character [ISO Standard Country Codes.](<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo13 = ShipTo13Builder::init()
    ->firstName('firstName0')
    ->lastName('lastName8')
    ->address1('address12')
    ->address2('address26')
    ->administrativeArea('administrativeArea0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

