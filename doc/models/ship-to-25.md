
# Ship to 25

*This model accepts additional fields of type array.*

## Structure

`ShipTo25`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>Optional field.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S. or<br>Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the billing address. Use the [State, Province, and Territory Codes for the United States and Canada](<br><br>For Payouts: This field may be sent only for FDC Compass.<br><br>##### Visa Acceptance through VisaNet<br><br>Credit card networks cannot process transactions that contain non-ASCII characters. Visa Acceptance through VisaNet<br>accepts and stores non-ASCII characters correctly and displays them correctly in reports. However, the limitations<br>of the credit card networks prevent Visa Acceptance through VisaNet from transmitting non-ASCII characters to the<br>credit card networks. Therefore, Visa Acceptance through VisaNet replaces non-ASCII characters with meaningless<br>ASCII characters for transmission to the credit card networks.<br><br>**Important** It is your responsibility to determine whether a field is required for the transaction you are requesting.<br><br>#### Chase Paymentech Solutions<br><br>Optional field.<br><br>#### Credit Mutuel-CIC<br><br>Optional field.<br><br>#### OmniPay Direct<br><br>Optional field.<br><br>#### SIX<br><br>Optional field.<br><br>#### TSYS Acquiring Solutions<br><br>Required when `processingInformation.billPaymentOptions.billPayment=true` and `pointOfSaleInformation.entryMode=keyed`.<br><br>#### Worldpay VAP<br><br>Optional field.<br><br>#### All other processors<br><br>Not used.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>Required field for authorization if any shipping address information is included in the request and<br>shipping to the U.S. or Canada; otherwise, optional.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>Example A1B 2C3<br><br>#### American Express Direct<br><br>Before sending the postal code to the processor, all nonalphanumeric characters are removed and, if the<br>remaining value is longer than nine characters, the value is truncated starting from the right side.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `32` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `company` | `?string` | Optional | Name of the customer’s company.<br><br>**Constraints**: *Maximum Length*: `60` | getCompany(): ?string | setCompany(?string company): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character [ISO Standard Country Codes.](<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `phoneNumber` | `?string` | Optional | Phone number associated with the shipping address.<br><br>**Constraints**: *Maximum Length*: `15` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo25Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo25 = ShipTo25Builder::init()
    ->firstName('firstName8')
    ->lastName('lastName0')
    ->address1('address14')
    ->address2('address28')
    ->locality('locality6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

