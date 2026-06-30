
# Line Item 11

*This model accepts additional fields of type array.*

## Structure

`LineItem11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `productCode` | `?string` | Optional | Type of product. This value is used to determine the category that the product is in: electronic, handling,<br>physical, service, or shipping. The default value is **default**.<br><br>For a payment, when you set this field to a value other than default or any of the values related to<br>shipping and handling, below fields _quantity_, _productName_, and _productSKU_ are required.<br><br>**Constraints**: *Maximum Length*: `255` | getProductCode(): ?string | setProductCode(?string productCode): void |
| `productName` | `?string` | Optional | For PAYMENT and CAPTURE API, this field is required when above _productCode_ is not **default** or one of the<br>values related to shipping and handling.<br><br>**Constraints**: *Maximum Length*: `255` | getProductName(): ?string | setProductName(?string productName): void |
| `productSku` | `?string` | Optional | Identification code for the product. For Payment and Capture APIs, this field is required when above<br>`productCode` is not **default** or one of the values related to shipping and/or handling.<br><br>**Constraints**: *Maximum Length*: `255` | getProductSku(): ?string | setProductSku(?string productSku): void |
| `taxAmount` | `?string` | Optional | Total tax to apply to the product. This value cannot be negative. The tax amount and the offer amount must<br>be in the same currency. The tax amount field is additive.<br><br>The following example uses a two-exponent currency such as USD:<br><br>1. You include each line item in your request.<br>   - 1st line item has `amount=10.00`, `quantity=1`, and `taxAmount=0.80`<br>   - 2nd line item has `amount=20.00`, `quantity=1`, and `taxAmount=1.60`<br>2. The total amount authorized will be 32.40, not 30.00 with 2.40 of tax included.<br><br>This field is frequently used for Level II and Level III transactions.<br><br>**Constraints**: *Maximum Length*: `15` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `quantity` | `?int` | Optional | For a payment or capture, this field is required when _productCode_ is not **default** or one of the values<br>related to shipping and handling.<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1`, `<= 999999999` | getQuantity(): ?int | setQuantity(?int quantity): void |
| `unitPrice` | `?string` | Optional | Per-item price of the product. This value cannot be negative. You can include a decimal point (.), but you<br>cannot include any other special characters. Visa Acceptance truncates the amount to the correct number of decimal<br>places.<br><br>**Constraints**: *Maximum Length*: `15` | getUnitPrice(): ?string | setUnitPrice(?string unitPrice): void |
| `fulfillmentType` | `?string` | Optional | The description for this field is not available. | getFulfillmentType(): ?string | setFulfillmentType(?string fulfillmentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem11Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$lineItem11 = LineItem11Builder::init()
    ->productCode('productCode6')
    ->productName('productName4')
    ->productSku('productSku4')
    ->taxAmount('taxAmount6')
    ->quantity(1)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

