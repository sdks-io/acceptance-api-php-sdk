
# Ship To

*This model accepts additional fields of type array.*

## Structure

`ShipTo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `title` | `?string` | Optional | The title of the person receiving the product.<br><br>**Constraints**: *Maximum Length*: `10` | getTitle(): ?string | setTitle(?string title): void |
| `firstName` | `?string` | Optional | First name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `middleName` | `?string` | Optional | Middle name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getMiddleName(): ?string | setMiddleName(?string middleName): void |
| `lastName` | `?string` | Optional | Last name of the recipient.<br><br>#### Litle<br><br>Maximum length: 25<br><br>#### All other processors<br><br>Maximum length: 60<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `address1` | `?string` | Optional | First line of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Second line of the shipping address.<br><br>Optional field.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `60` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City of the shipping address.<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S. or<br>Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province of the shipping address. Use the [State, Province, and Territory Codes for the United States and Canada]( (maximum length: 2)<br><br>Required field for authorization if any shipping address information is included in the request and shipping to the U.S.<br>or Canada; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code for the shipping address. The postal code must consist of 5 to 9 digits.<br><br>Required field for authorization if any shipping address information is included in the request and<br>shipping to the U.S. or Canada; otherwise, optional.<br><br>When the billing country is the U.S., the 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br><br>Example 12345-6789<br><br>When the billing country is Canada, the 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space][numeric][alpha][numeric]<br><br>Example A1B 2C3<br><br>#### American Express Direct<br><br>Before sending the postal code to the processor, all nonalphanumeric characters are removed and, if the<br>remaining value is longer than nine characters, the value is truncated starting from the right side.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `32` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `county` | `?string` | Optional | U.S. county if available.<br><br>**Constraints**: *Maximum Length*: `50` | getCounty(): ?string | setCounty(?string county): void |
| `country` | `?string` | Optional | Country of the shipping address. Use the two-character [ISO Standard Country Codes.](<br><br>Required field for authorization if any shipping address information is included in the request; otherwise, optional.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br>Billing address objects will be used to determine the cardholder’s location when shipTo objects are not present.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `district` | `?string` | Optional | Neighborhood, community, or region within a city or municipality.<br><br>**Constraints**: *Maximum Length*: `50` | getDistrict(): ?string | setDistrict(?string district): void |
| `buildingNumber` | `?string` | Optional | Building number in the street address. For example, the building number is 187 in the following address:<br><br>Rua da Quitanda 187<br><br>**Constraints**: *Maximum Length*: `15` | getBuildingNumber(): ?string | setBuildingNumber(?string buildingNumber): void |
| `phoneNumber` | `?string` | Optional | Phone number associated with the shipping address.<br><br>**Constraints**: *Maximum Length*: `15` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `email` | `?string` | Optional | Email of the recipient.<br><br>**Constraints**: *Maximum Length*: `255` | getEmail(): ?string | setEmail(?string email): void |
| `company` | `?string` | Optional | Name of the customer’s company.<br><br>**Constraints**: *Maximum Length*: `60` | getCompany(): ?string | setCompany(?string company): void |
| `destinationTypes` | `?string` | Optional | Shipping destination of item. Example: Commercial, Residential, Store<br><br>**Constraints**: *Maximum Length*: `25` | getDestinationTypes(): ?string | setDestinationTypes(?string destinationTypes): void |
| `destinationCode` | `?int` | Optional | Indicates destination chosen for the transaction. Possible values:<br><br>- 01- Ship to cardholder billing address<br>- 02- Ship to another verified address on file with merchant<br>- 03- Ship to address that is different than billing address<br>- 04- Ship to store (store address should be populated on request)<br>- 05- Digital goods<br>- 06- Travel and event tickets, not shipped<br>- 07- Other | getDestinationCode(): ?int | setDestinationCode(?int destinationCode): void |
| `method` | `?string` | Optional | Shipping method for the product. Possible values:<br><br>- lowcost: Lowest-cost service<br>- sameday: Courier or same-day service<br>- oneday: Next-day or overnight service<br>- twoday: Two-day service<br>- threeday: Three-day service<br>- pickup: Store pick-up<br>- other: Other shipping method<br>- none: No shipping method because product is a service or subscription<br>  Required for American Express SafeKey (U.S.).<br><br>**Constraints**: *Maximum Length*: `10` | getMethod(): ?string | setMethod(?string method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipToBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shipTo = ShipToBuilder::init()
    ->title('title0')
    ->firstName('firstName0')
    ->middleName('middleName2')
    ->lastName('lastName8')
    ->address1('address12')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

