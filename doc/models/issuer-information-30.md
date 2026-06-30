
# Issuer Information 30

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation30`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | This field contains the issuer name.<br><br>**Constraints**: *Maximum Length*: `200` | getName(): ?string | setName(?string name): void |
| `country` | `?string` | Optional | This field contains [2-character ISO Country Codes]( for the issuer.<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `binLength` | `?string` | Optional | This field contains the length of the BIN.<br><br>**Constraints**: *Maximum Length*: `2` | getBinLength(): ?string | setBinLength(?string binLength): void |
| `phoneNumber` | `?string` | Optional | This field contains the customer service phone number for the issuer.<br><br>**Constraints**: *Maximum Length*: `50` | getPhoneNumber(): ?string | setPhoneNumber(?string phoneNumber): void |
| `transactionInformation` | `?string` | Optional | In a Mastercard Transaction, this field contains the unique identifier (Transaction Link ID) for the first transaction in a transaction life cycle.<br>This ID is crucial for maintaining continuity and linking subsequent operations to the original transaction.<br><br>**Constraints**: *Maximum Length*: `36` | getTransactionInformation(): ?string | setTransactionInformation(?string transactionInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation30Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation30 = IssuerInformation30Builder::init()
    ->name('name8')
    ->country('country2')
    ->binLength('binLength8')
    ->phoneNumber('phoneNumber8')
    ->transactionInformation('transactionInformation6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

