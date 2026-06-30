
# Merchant Defined Information 7

*This model accepts additional fields of type array.*

## Structure

`MerchantDefinedInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | The number you assign as the name for your merchant-defined data or secure field. Possible Values are data1 to data4 and sensitive1 to sensitive4<br><br>For example, to set the name for merchant-defined data 2 field, you would reference merchantDefinedInformation[x].name as data2<br>Possible Values:<br><br>- data1<br>- data2<br>- data3<br>- data4<br>- sensitive1<br>- sensitive2<br>- sensitive3<br>- sensitive4 | getName(): ?string | setName(?string name): void |
| `value` | `?string` | Optional | The value you assign for your merchant-defined data field.<br><br>**Warning** Merchant-defined data fields are not intended to and must not be used to capture personally identifying information. Accordingly, merchants are prohibited from capturing, obtaining, and/or transmitting any personally identifying information in or via the merchant-defined data fields. Personally identifying information includes, but is not<br>limited to, address, credit card number, social security number, driver's license number, state-issued identification number, passport number, and card verification numbers (CVV,<br>CVC2, CVV2, CID, CVN). In the event it is discovered a merchant is capturing and/or transmitting personally identifying information via the merchant-defined data fields, whether or not intentionally, the merchant's account will immediately be suspended, which will result in a rejection of any and all transaction requests submitted by the merchant after the point of suspension.<br><br>**Constraints**: *Maximum Length*: `100` | getValue(): ?string | setValue(?string value): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDefinedInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$merchantDefinedInformation7 = MerchantDefinedInformation7Builder::init()
    ->name('name2')
    ->value('value4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

