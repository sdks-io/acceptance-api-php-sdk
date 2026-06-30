
# Tax Details 1

*This model accepts additional fields of type array.*

## Structure

`TaxDetails1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Indicates the type of tax data for the _taxDetails_ object.<br><br>Possible values:<br><br>- `alternate`<br>- `local`<br>- `national`<br>- `vat`<br>- `other`<br>- `green` | getType(): ?string | setType(?string type): void |
| `amount` | `?string` | Optional | Indicates the amount of tax based on the `type` field as described in the table below:<br><br>\| type      \| type description \|<br>\| ------------- \|:-------------:\|<br>\| `alternate` \| Total amount of alternate tax for the order. \|<br>\| `local`     \| Sales tax for the order. \|<br>\| `national`  \| National tax for the order. \|<br>\| `vat`       \| Total amount of value added tax (VAT) included in the order. \|<br>\| `other`     \| Other tax. \|<br>\| `green`     \| Green tax amount for Korean Processing. \|<br><br>**Constraints**: *Maximum Length*: `13` | getAmount(): ?string | setAmount(?string amount): void |
| `rate` | `?string` | Optional | Rate of VAT or other tax for the order.<br><br>Example 0.040 (=4%)<br><br>Valid range: 0.01 to 0.99 (1% to 99%, with only whole percentage values accepted; values with additional<br>decimal places will be truncated)<br><br>**Constraints**: *Maximum Length*: `6` | getRate(): ?string | setRate(?string rate): void |
| `code` | `?string` | Optional | Type of tax being applied to the item.<br><br>#### FDC Nashville Global<br><br>- `alternate_tax_type_applied`<br>- `alternate_tax_type_identifier`<br><br>#### Worldpay VAP<br><br>- `alternate_tax_type_identifier`<br><br>#### RBS WorldPay Atlanta<br><br>- `tax_type_applied`<br><br>#### TSYS Acquiring Solutions<br><br>- `tax_type_applied`<br>- `local_tax_indicator`<br><br>#### Chase Paymentech Solutions<br><br>- `tax_type_applied`<br><br>#### Elavon Americas<br><br>- `local_tax_indicator`<br><br>#### FDC Compass<br><br>- `tax_type_applied`<br><br>#### OmniPay Direct<br><br>- `local_tax_indicator`<br><br>**Constraints**: *Maximum Length*: `4` | getCode(): ?string | setCode(?string code): void |
| `taxId` | `?string` | Optional | Your tax ID number to use for the alternate tax amount. Required if you set alternate tax amount to any value,<br>including zero. You may send this field without sending alternate tax amount.<br><br>**Constraints**: *Maximum Length*: `15` | getTaxId(): ?string | setTaxId(?string taxId): void |
| `applied` | `?bool` | Optional | Flag that indicates whether the alternate tax amount (`orderInformation.amountDetails.taxDetails[].amount`) is<br>included in the request.<br><br>Possible values:<br><br>- `false`: alternate tax amount is not included in the request.<br>- `true`: alternate tax amount is included in the request. | getApplied(): ?bool | setApplied(?bool applied): void |
| `exemptionCode` | `?string` | Optional | Status code for exemption from sales and use tax. This field is a pass-through, which means that<br>Visa Acceptance does not verify the value or modify it in any way before sending it to the processor.<br><br>**Constraints**: *Maximum Length*: `1` | getExemptionCode(): ?string | setExemptionCode(?string exemptionCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TaxDetails1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$taxDetails1 = TaxDetails1Builder::init()
    ->type('type2')
    ->amount('amount0')
    ->rate('rate2')
    ->code('code6')
    ->taxId('taxId4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

