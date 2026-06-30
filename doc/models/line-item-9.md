
# Line Item 9

*This model accepts additional fields of type array.*

## Structure

`LineItem9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `productName` | `?string` | Optional | For an authorization or capture transaction (`processingOptions.capture` is `true` or `false`),<br>this field is required when `orderInformation.lineItems[].productCode` is not `default` or one of<br>the other values that are related to shipping and/or handling.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br><br>**Constraints**: *Maximum Length*: `255` | getProductName(): ?string | setProductName(?string productName): void |
| `productDescription` | `?string` | Optional | Brief description of item. | getProductDescription(): ?string | setProductDescription(?string productDescription): void |
| `productSku` | `?string` | Optional | Product identifier code. Also known as the Stock Keeping Unit (SKU) code for the product.<br><br>For an authorization or capture transaction (`processingOptions.capture` is set to `true` or `false`), this field is required when `orderInformation.lineItems[].productCode` is not set to **default** or one of the other values that are related to shipping and/or handling.<br><br>#### Tax Calculation<br><br>Optional field for U.S. and Canadian taxes. Not applicable to international and value added taxes.<br>For an authorization or capture transaction (`processingOptions.capture` is set to `true` or `false`), this field is<br>required when `orderInformation.lineItems[].productCode` is not `default` or one of the values related to shipping and/or handling.<br><br>**Constraints**: *Maximum Length*: `255` | getProductSku(): ?string | setProductSku(?string productSku): void |
| `quantity` | `?int` | Optional | Number of units for this order. Must be a non-negative integer.<br><br>The default is `1`. For an authorization or capture transaction (`processingOptions.capture` is set to `true` or `false`),<br>this field is required when `orderInformation.lineItems[].productCode` is not `default` or one of the other values<br>related to shipping and/or handling.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1`, `<= 999999999` | getQuantity(): ?int | setQuantity(?int quantity): void |
| `typeOfSupply` | `?string` | Optional | Flag to indicate whether the purchase is categorized as goods or services.<br>Possible values:<br><br>- 00: goods<br>- 01: services<br><br>**Constraints**: *Maximum Length*: `2` | getTypeOfSupply(): ?string | setTypeOfSupply(?string typeOfSupply): void |
| `unitPrice` | `?string` | Optional | Per-item price of the product. This value for this field cannot be negative.<br><br>You must include either this field or the request-level field `orderInformation.amountDetails.totalAmount` in your request.<br><br>You can include a decimal point (.), but you cannot include any other special characters.<br>The value is truncated to the correct number of decimal places.<br><br>#### DCC with a Third-Party Provider<br><br>Set this field to the converted amount that was returned by the DCC provider. You must include either<br>the 1st line item in the order and this field, or the request-level field `orderInformation.amountDetails.totalAmount` in your request.<br><br>#### Tax Calculation<br><br>Required field for U.S., Canadian, international and value added taxes.<br><br>#### Zero Amount Authorizations<br><br>If your processor supports zero amount authorizations, you can set this field to 0 for the<br>authorization to check if the card is lost or stolen.<br><br>#### Maximum Field Lengths<br><br>For GPN and JCN Gateway: Decimal (10)<br>All other processors: Decimal (15)<br><br>**Constraints**: *Maximum Length*: `15` | getUnitPrice(): ?string | setUnitPrice(?string unitPrice): void |
| `totalAmount` | `?string` | Optional | Total amount for the item. Normally calculated as the unit price times quantity.<br><br>When `orderInformation.lineItems[].productCode` is "gift_card", this is the purchase amount total<br>for prepaid gift cards in major units.<br><br>Example: 123.45 USD = 123<br><br>**Constraints**: *Maximum Length*: `13` | getTotalAmount(): ?string | setTotalAmount(?string totalAmount): void |
| `taxAmount` | `?string` | Optional | Total tax to apply to the product. This value cannot be negative. The tax amount and the offer amount must<br>be in the same currency. The tax amount field is additive.<br><br>The following example uses a two-exponent currency such as USD:<br><br>1. You include each line item in your request.<br>   ..- 1st line item has amount=10.00, quantity=1, and taxAmount=0.80<br>   ..- 2nd line item has amount=20.00, quantity=1, and taxAmount=1.60<br>2. The total amount authorized will be 32.40, not 30.00 with 2.40 of tax included.<br><br>Optional field.<br><br>#### Airlines processing<br><br>Tax portion of the order amount. This value cannot exceed 99999999999999 (fourteen 9s).<br>Format: English characters only.<br>Optional request field for a line item.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br><br>Note if you send this field in your tax request, the value in the field will override the tax engine<br><br>**Constraints**: *Maximum Length*: `15` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$lineItem9 = LineItem9Builder::init()
    ->productName('productName0')
    ->productDescription('productDescription8')
    ->productSku('productSku0')
    ->quantity(1)
    ->typeOfSupply('typeOfSupply0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

