
# Merchant Descriptor 13

*This model accepts additional fields of type array.*

## Structure

`MerchantDescriptor13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `alternateName` | `?string` | Optional | Alternate contact information for your business,such as an email address or URL.<br>This value might be displayed on the cardholder’s statement.<br>When you do not include this value in your capture or credit request, the merchant URL from your Visa Acceptance account is used.<br>Important This value must consist of English characters<br><br>**Constraints**: *Maximum Length*: `13` | getAlternateName(): ?string | setAlternateName(?string alternateName): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDescriptor13 = MerchantDescriptor13Builder::init()
    ->alternateName('alternateName8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

