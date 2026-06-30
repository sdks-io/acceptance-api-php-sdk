
# Merchant Defined Information

*This model accepts additional fields of type array.*

## Structure

`MerchantDefinedInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `key` | `?string` | Optional | The number you assign for as the key for your merchant-defined data field. Valid values are 0 to 100.<br><br>For example, to set or access the key for the 2nd merchant-defined data field in the array, you would reference `merchantDefinedInformation[1].key`.<br><br>#### Visa Acceptance through VisaNet<br><br>For installment payments with Mastercard in Brazil, use `merchantDefinedInformation[0].key` and<br>`merchantDefinedInformation[1].key` for data that you want to provide to the issuer to identify the<br>transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getKey(): ?string | setKey(?string key): void |
| `value` | `?string` | Optional | The value you assign for your merchant-defined data field.<br><br>**Warning** Merchant-defined data fields are not intended to and must not be used to capture personally identifying information. Accordingly, merchants are prohibited from capturing, obtaining, and/or transmitting any personally identifying information in or via the merchant-defined data fields. Personally identifying information includes, but is not<br>limited to, address, credit card number, social security number, driver's license number, state-issued identification number, passport number, and card verification numbers (CVV,<br>CVC2, CVV2, CID, CVN). In the event Visa Acceptance discovers that a merchant is capturing and/or transmitting personally identifying information via the merchant-defined data fields, whether or not intentionally, Visa Acceptance will immediately suspend the merchant's account, which will result in a rejection of any and all transaction requests submitted by the merchant after the point of suspension.<br><br>#### Visa Acceptance through VisaNet<br><br>For installment payments with Mastercard in Brazil, use `merchantDefinedInformation[0].value` and<br>`merchantDefinedInformation[1].value` for data that you want to provide to the issuer to identify the<br>transaction.<br><br>For installment payments with Mastercard in Brazil:<br><br>- The value for merchantDefinedInformation[0].value corresponds to the following data in the TC 33 capture file5:<br>  - Record: CP07 TCR5<br>  - Position: 25-44<br>  - Field: Reference Field 2<br>- The value for merchantDefinedInformation[1].value corresponds to the following data in the TC 33 capture file5:<br>  - Record: CP07 TCR5<br>  - Position: 45-64<br>  - Field: Reference Field 3<br><br>**Constraints**: *Maximum Length*: `800` | getValue(): ?string | setValue(?string value): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDefinedInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDefinedInformation = MerchantDefinedInformationBuilder::init()
    ->key('key8')
    ->value('value0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

