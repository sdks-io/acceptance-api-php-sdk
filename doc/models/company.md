
# Company

*This model accepts additional fields of type array.*

## Structure

`Company`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the customer’s company.<br><br>**Visa Acceptance through VisaNet**<br>Credit card networks cannot process transactions that contain non-ASCII characters. Visa Acceptance through VisaNet accepts and stores non-ASCII characters correctly and displays them correctly in reports. However, the limitations of the credit card networks prevent Visa Acceptance through VisaNet from transmitting non-ASCII characters to the credit card networks. Therefore, Visa Acceptance through VisaNet replaces non-ASCII characters with meaningless ASCII characters for transmission to the credit card networks.<br><br>**Constraints**: *Maximum Length*: `60` | getName(): ?string | setName(?string name): void |
| `address1` | `?string` | Optional | First line in the street address of the company purchasing the product.<br><br>**Constraints**: *Maximum Length*: `40` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Additional address information for the company purchasing the product.<br><br>**Constraints**: *Maximum Length*: `40` | getAddress2(): ?string | setAddress2(?string address2): void |
| `locality` | `?string` | Optional | City in the address of the company purchasing the product.<br><br>**Constraints**: *Maximum Length*: `30` | getLocality(): ?string | setLocality(?string locality): void |
| `administrativeArea` | `?string` | Optional | State or province in the address of the company purchasing the product. Use the State, Province, and Territory<br>Codes for the United States and Canada.<br><br>**Constraints**: *Maximum Length*: `50` | getAdministrativeArea(): ?string | setAdministrativeArea(?string administrativeArea): void |
| `postalCode` | `?string` | Optional | Postal code in the address of the company purchasing the product. The postal code must consist of 5 to 9 digits.<br><br>When the company country is the U.S., the 9-digit postal code must follow this format:<br>**[5 digits][dash][4 digits]**<br><br>#### Example<br><br>`12345-6789`<br><br>When the company country is Canada, the 6-digit postal code must follow this format:<br>**[alpha][numeric][alpha][space][numeric][alpha][numeric]**<br><br>#### Example<br><br>`A1B 2C3`<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `country` | `?string` | Optional | Country in the address of the company purchasing the product. Use the [ISO Standard Country Codes](<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CompanyBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$company = CompanyBuilder::init()
    ->name('name0')
    ->address1('address18')
    ->address2('address22')
    ->locality('locality0')
    ->administrativeArea('administrativeArea6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

