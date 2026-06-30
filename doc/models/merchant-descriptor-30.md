
# Merchant Descriptor 30

*This model accepts additional fields of type array.*

## Structure

`MerchantDescriptor30`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Your merchant name.<br><br>**Note** For Paymentech processor using Visa Acceptance Payouts, the maximum data length is 22.<br><br>#### PIN debit<br><br>Your business name. This name is displayed on the cardholder’s statement. When you<br>include more than one consecutive space, extra spaces are removed.<br><br>When you do not include this value in your PIN debit request, the merchant name from your account is used.<br>**Important** This value must consist of English characters.<br><br>Optional field for PIN debit credit or PIN debit purchase requests.<br><br>#### Airline processing<br><br>Your merchant name. This name is displayed on the cardholder’s statement. When you include more than one consecutive space, extra spaces are removed.<br><br>**Note** Some airline fee programs may require the original ticket number (ticket identifier) or the ancillary service description in positions 13 through 23 of this field.<br><br>**Important** This value must consist of English characters.<br><br>Required for captures and credits. | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor30Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDescriptor30 = MerchantDescriptor30Builder::init()
    ->name('name6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

