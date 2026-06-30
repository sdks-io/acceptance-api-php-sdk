
# Tax Details

*This model accepts additional fields of type array.*

## Structure

`TaxDetails`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amount` | `?string` | Optional | Indicates the amount of tax based on the `type` field as described in the table below:<br><br>**Constraints**: *Maximum Length*: `13` | getAmount(): ?string | setAmount(?string amount): void |
| `rate` | `?string` | Optional | Rate of VAT or other tax for the order.<br><br>Example 0.040 (=4%)<br><br>Valid range: 0.01 to 0.99 (1% to 99%, with only whole percentage values accepted; values with additional<br>decimal places will be truncated)<br><br>**Constraints**: *Maximum Length*: `6` | getRate(): ?string | setRate(?string rate): void |
| `applied` | `?bool` | Optional | Flag that indicates whether the tax amount (`travelInformation.autoRental.taxDetails.amount`) is<br>included in the request.<br><br>Possible values:<br><br>- `false`: tax amount is not included in the request.<br>- `true`:  tax amount is included in the request. | getApplied(): ?bool | setApplied(?bool applied): void |
| `exemptionCode` | `?string` | Optional | Status code for exemption from sales and use tax. This field is a pass-through, which means that<br>Visa Acceptance does not verify the value or modify it in any way before sending it to the processor.<br><br>**Constraints**: *Maximum Length*: `1` | getExemptionCode(): ?string | setExemptionCode(?string exemptionCode): void |
| `taxType` | `?string` | Optional | Different taxes the rental agency applies to the rental agreement such as tourist tax, airport tax, or rental tax.<br><br>**Constraints**: *Maximum Length*: `10` | getTaxType(): ?string | setTaxType(?string taxType): void |
| `taxSummary` | `?string` | Optional | Summary of all tax types<br><br>**Constraints**: *Maximum Length*: `12` | getTaxSummary(): ?string | setTaxSummary(?string taxSummary): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TaxDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$taxDetails = TaxDetailsBuilder::init()
    ->amount('amount6')
    ->rate('rate6')
    ->applied(false)
    ->exemptionCode('exemptionCode0')
    ->taxType('taxType2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

