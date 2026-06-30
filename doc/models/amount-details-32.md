
# Amount Details 32

*This model accepts additional fields of type array.*

## Structure

`AmountDetails32`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | Grand total for the order. This value cannot be negative. You can include a decimal point (.), but you cannot include any other special characters. Visa Acceptance truncates the amount to the correct number of decimal places<br><br>**Constraints**: *Maximum Length*: `32` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `currency` | `?string` | Optional | Currency used for the order<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `discountAmount` | `?string` | Optional | Discount amount for the transaction.<br><br>**Constraints**: *Maximum Length*: `32` | getDiscountAmount(): ?string | setDiscountAmount(?string discountAmount): void |
| `shippingAmount` | `?string` | Optional | Aggregate shipping charges for the transactions.<br><br>**Constraints**: *Maximum Length*: `32` | getShippingAmount(): ?string | setShippingAmount(?string shippingAmount): void |
| `shippingDiscountAmount` | `?string` | Optional | Shipping discount amount for the transaction.<br><br>**Constraints**: *Maximum Length*: `32` | getShippingDiscountAmount(): ?string | setShippingDiscountAmount(?string shippingDiscountAmount): void |
| `taxAmount` | `?string` | Optional | Total tax amount.<br><br>**Constraints**: *Maximum Length*: `32` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `insuranceAmount` | `?string` | Optional | Amount being charged for the insurance fee.<br><br>**Constraints**: *Maximum Length*: `32` | getInsuranceAmount(): ?string | setInsuranceAmount(?string insuranceAmount): void |
| `dutyAmount` | `?string` | Optional | Amount being charged as duty amount.<br><br>**Constraints**: *Maximum Length*: `32` | getDutyAmount(): ?string | setDutyAmount(?string dutyAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails32Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails32 = AmountDetails32Builder::init()
    ->totalAmount('totalAmount2')
    ->currency('currency8')
    ->discountAmount('discountAmount0')
    ->shippingAmount('shippingAmount2')
    ->shippingDiscountAmount('shippingDiscountAmount8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

