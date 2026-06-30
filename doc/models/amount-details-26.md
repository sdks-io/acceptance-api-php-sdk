
# Amount Details 26

*This model accepts additional fields of type array.*

## Structure

`AmountDetails26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalAmount` | `?string` | Optional | Grand total for the order. This value cannot be negative. You can include a decimal point (.), but you cannot include any other special characters. Visa Acceptance truncates the amount to the correct number of decimal places<br><br>**Constraints**: *Maximum Length*: `10` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `currency` | `?string` | Optional | Currency used for the order<br><br>**Constraints**: *Maximum Length*: `5` | getCurrency(): ?string | setCurrency(?string currency): void |
| `subTotalAmount` | `?string` | Optional | Shipping discount amount for the transaction. If this amount has changed since the initial sessions request, you must include the new value in the order request. You must also include all additional amount fields that apply to the order and ensure the total amount equals the purchaseTotals_grandTotalAmount value.<br><br>**Constraints**: *Maximum Length*: `15` | getSubTotalAmount(): ?string | setSubTotalAmount(?string subTotalAmount): void |
| `handlingAmount` | `?string` | Optional | Aggregate handling charges for the transaction. If this amount has changed since the initial sessions request, you must include the new value in the order request. You must also include all additional amount fields that apply to the order and ensure the total amount equals the purchaseTotals_grandTotalAmount value.<br><br>**Constraints**: *Maximum Length*: `15` | getHandlingAmount(): ?string | setHandlingAmount(?string handlingAmount): void |
| `shippingAmount` | `?string` | Optional | Aggregate shipping charges for the transaction If this amount has changed since the initial sessions request, you must include the new value in the order request. You must also include all additional amount fields that apply to the order and ensure the total amount equals the purchaseTotals_grandTotalAmount value.<br><br>**Constraints**: *Maximum Length*: `15` | getShippingAmount(): ?string | setShippingAmount(?string shippingAmount): void |
| `shippingDiscountAmount` | `?string` | Optional | Shipping discount amount for the transaction. If this amount has changed since the initial sessions request, you must include the new value in the order request. You must also include all additional amount fields that apply to the order and ensure the total amount equals the purchaseTotals_grandTotalAmount value.<br><br>**Constraints**: *Maximum Length*: `15` | getShippingDiscountAmount(): ?string | setShippingDiscountAmount(?string shippingDiscountAmount): void |
| `taxAmount` | `?string` | Optional | Total tax amount. When the purchaseTotals_ taxAmount and ap_subtotalAmount fields are included in the request, do not include the tax amount as part of the subtotal amount calculation.<br><br>**Constraints**: *Maximum Length*: `10` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `insuranceAmount` | `?string` | Optional | Amount being charged for the insurance fee. Only supported when the payment_method is set to paypal.<br><br>**Constraints**: *Maximum Length*: `15` | getInsuranceAmount(): ?string | setInsuranceAmount(?string insuranceAmount): void |
| `giftWrapAmount` | `?string` | Optional | Amount being charged as gift wrap fee.<br><br>**Constraints**: *Maximum Length*: `15` | getGiftWrapAmount(): ?string | setGiftWrapAmount(?string giftWrapAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails26 = AmountDetails26Builder::init()
    ->totalAmount('totalAmount2')
    ->currency('currency8')
    ->subTotalAmount('subTotalAmount8')
    ->handlingAmount('handlingAmount4')
    ->shippingAmount('shippingAmount8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

