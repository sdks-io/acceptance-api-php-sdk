
# Ship to 11

*This model accepts additional fields of type array.*

## Structure

`ShipTo11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>Optional field.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S. or<br>Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address. Use the [State, Province, and Territory Codes for the United States and Canada]( (maximum length: 2)<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S.<br>or Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>Required field for authorization if any shipping address information is included in the request and<br>shipping to the U.S. or Canada; otherwise, optional.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>Example A1B 2C3<br><br>#### American Express Direct<br><br>Before sending the postal code to the processor, all nonalphanumeric characters are removed and, if the<br>remaining value is longer than nine characters, the value is truncated starting from the right side.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `32` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character [ISO Standard Country Codes.](<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `method` | `?string` | Optional | Shipping method for the product. Possible values:<br><br>- lowcost: Lowest-cost service<br>- sameday: Courier or same-day service<br>- oneday: Next-day or overnight service<br>- twoday: Two-day service<br>- threeday: Three-day service<br>- pickup: Store pick-up<br>- other: Other shipping method<br>- none: No shipping method because product is a service or subscription<br>  Required for American Express SafeKey (U.S.).<br><br>**Constraints**: *Maximum Length*: `10` | getMethod(): ?string | setMethod(?string method): void |
| `email` | `?string` | Optional | Customer's email address, including the full domain name. | getEmail(): ?string | setEmail(?string email): void |
| `phoneNumber` | `?string` | Optional | Phone number associated with the shipping address. | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo11 = ShipTo11Builder::init()
    ->firstName('firstName2')
    ->lastName('lastName6')
    ->address1('address10')
    ->address2('address24')
    ->locality('locality2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

