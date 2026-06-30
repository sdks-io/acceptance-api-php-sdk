
# Acquirer Information

*This model accepts additional fields of type array.*

## Structure

`AcquirerInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `acquirerBin` | `?string` | Optional | Acquirer bank ID number that  corresponds to a certificate that Visa Acceptance already has.This ID has this format. 4XXXXX for Visa and 5XXXXX for Mastercard.<br><br>**Constraints**: *Maximum Length*: `11` | getAcquirerBin(): ?string | setAcquirerBin(?string acquirerBin): void |
| `country` | `?string` | Optional | Issuers need to be aware of the Acquirer's Country Code when the Acquirer country differs from the Merchant country and the Acquirer is in the EEA (European Economic Area).<br><br>**Constraints**: *Maximum Length*: `2` | getCountry(): ?string | setCountry(?string country): void |
| `password` | `?string` | Optional | Registered password for the Visa directory server.<br><br>**Constraints**: *Maximum Length*: `8` | getPassword(): ?string | setPassword(?string password): void |
| `merchantId` | `?string` | Optional | Username for the visa directory server that is created when your acquirer sets up your account. This ID might be the same as your merchant ID. the username can be 15 or 23 characters.<br><br>**Constraints**: *Maximum Length*: `15` | getMerchantId(): ?string | setMerchantId(?string merchantId): void |
| `acquirerMerchantId` | `?string` | Optional | Acquirer assigned merchant id. Check if your processor supports this field.<br><br>**Constraints**: *Maximum Length*: `15` | getAcquirerMerchantId(): ?string | setAcquirerMerchantId(?string acquirerMerchantId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AcquirerInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$acquirerInformation = AcquirerInformationBuilder::init()
    ->acquirerBin('acquirerBin4')
    ->country('country2')
    ->password('password2')
    ->merchantId('merchantId4')
    ->acquirerMerchantId('acquirerMerchantId0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

