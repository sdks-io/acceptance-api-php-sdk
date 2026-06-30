
# Issuer Information 6

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | This field contains the issuer name.<br><br>**Constraints**: *Maximum Length*: `200` | getName(): ?string | setName(?string name): void |
| `country` | `?string` | Optional | This field contains [2-character ISO Country Codes]( for the issuer.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `binLength` | `?string` | Optional | This field contains the length of the BIN. In some cases, this field may be absent if we do not receive accurate information from the network source.<br><br>**Constraints**: *Maximum Length*: `2` | getBinLength(): ?string | setBinLength(?string binLength): void |
| `accountPrefix` | `?string` | Optional | This field contains the first 6 to 8 digits of a primary account number (PAN). The length of the field is determined by [PCI-DSS standards for truncation]( case the input is not the full intrument (PAN or TOKEN), this field may be truncated.<br><br>**Constraints**: *Maximum Length*: `8` | getAccountPrefix(): ?string | setAccountPrefix(?string accountPrefix): void |
| `phoneNumber` | `?string` | Optional | This field contains the customer service phone number for the issuer.<br><br>**Constraints**: *Maximum Length*: `50` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation6 = IssuerInformation6Builder::init()
    ->name('name6')
    ->country('country0')
    ->binLength('binLength6')
    ->accountPrefix('accountPrefix8')
    ->phoneNumber('phoneNumber4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

