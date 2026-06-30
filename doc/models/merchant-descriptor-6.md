
# Merchant Descriptor 6

*This model accepts additional fields of type array.*

## Structure

`MerchantDescriptor6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `postalCode` | `?string` | Optional | Merchant's postal code.<br><br>#### PIN debit<br><br>Postal code for your business location. This value might be displayed on the cardholder’s statement.<br><br>If your business is domiciled in the U.S., you can use a 5-digit or 9-digit postal code. A 9-digit postal code must follow this format:<br>[5 digits][dash][4 digits]<br>Example: `12345-6789`<br><br>If your business is domiciled in Canada, you can use a 6-digit or 9-digit postal code. A 6-digit postal code must follow this format:<br>[alpha][numeric][alpha][space]<br>[numeric][alpha][numeric]<br>Example: `A1B 2C3`<br><br>When you do not include this value in your PIN debit request, the merchant name from your account is used.<br>**Important** This value must consist of English characters.<br><br>**Note** This field is supported only for businesses located in the U.S. or Canada.<br>**Important** Mastercard requires a postal code for any country that uses postal codes.<br>You can provide the postal code in your account or you can include this field in your request.<br><br>Optional field for PIN debit credit or PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `14` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `contact` | `?string` | Optional | Contact information for the merchant.<br><br>**Note** These are the maximum data lengths for the following payment processors:<br><br>- FDCCompass (13)<br>- Paymentech (13)<br><br>**Constraints**: *Maximum Length*: `14` | getContact(): ?string | setContact(?string contact): void |
| `locality` | `?string` | Optional | Merchant's City.<br><br>#### PIN debit<br><br>City for your business location. This value might be displayed on the cardholder’s statement.<br><br>When you do not include this value in your PIN debit request, the merchant name from your account is used.<br>**Important** This value must consist of English characters.<br><br>Optional field for PIN debit credit or PIN debit purchase requests.<br><br>**Constraints**: *Maximum Length*: `30` | getLocality(): ?string | setLocality(?string locality): void |
| `name` | `?string` | Optional | Your merchant name.<br><br>**Note** For Paymentech processor using Visa Acceptance Payouts, the maximum data length is 22.<br><br>#### PIN debit<br><br>Your business name. This name is displayed on the cardholder’s statement. When you<br>include more than one consecutive space, extra spaces are removed.<br><br>When you do not include this value in your PIN debit request, the merchant name from your account is used.<br>**Important** This value must consist of English characters.<br><br>Optional field for PIN debit credit or PIN debit purchase requests.<br><br>#### Airline processing<br><br>Your merchant name. This name is displayed on the cardholder’s statement. When you include more than one consecutive space, extra spaces are removed.<br><br>**Note** Some airline fee programs may require the original ticket number (ticket identifier) or the ancillary service description in positions 13 through 23 of this field.<br><br>**Important** This value must consist of English characters.<br><br>Required for captures and credits. | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDescriptor6 = MerchantDescriptor6Builder::init()
    ->postalCode('postalCode8')
    ->contact('contact2')
    ->locality('locality0')
    ->name('name0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

