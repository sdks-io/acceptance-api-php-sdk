
# Line Item 1

*This model accepts additional fields of type array.*

## Structure

`LineItem1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `quantity` | `?int` | Optional | Number of units for this order. Must be a non-negative integer.<br><br>The default is `1`. For an authorization or capture transaction (`processingOptions.capture` is set to `true` or `false`),<br>this field is required when `orderInformation.lineItems[].productCode` is not `default` or one of the other values<br>related to shipping and/or handling.<br><br>#### Tax Calculation<br><br>Optional field for U.S., Canadian, international tax, and value added taxes.<br><br>**Default**: `1`<br><br>**Constraints**: `>= 1`, `<= 999999999` | getQuantity(): ?int | setQuantity(?int quantity): void |
| `unitPrice` | `?string` | Optional | Per-item price of the product. This value for this field cannot be negative.<br><br>You must include either this field or the request-level field `orderInformation.amountDetails.totalAmount` in your request.<br><br>You can include a decimal point (.), but you cannot include any other special characters.<br>The value is truncated to the correct number of decimal places.<br><br>#### DCC with a Third-Party Provider<br><br>Set this field to the converted amount that was returned by the DCC provider. You must include either<br>the 1st line item in the order and this field, or the request-level field `orderInformation.amountDetails.totalAmount` in your request.<br><br>#### Tax Calculation<br><br>Required field for U.S., Canadian, international and value added taxes.<br><br>#### Zero Amount Authorizations<br><br>If your processor supports zero amount authorizations, you can set this field to 0 for the<br>authorization to check if the card is lost or stolen.<br><br>#### Maximum Field Lengths<br><br>For GPN and JCN Gateway: Decimal (10)<br>All other processors: Decimal (15)<br><br>**Constraints**: *Maximum Length*: `15` | getUnitPrice(): ?string | setUnitPrice(?string unitPrice): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$lineItem1 = LineItem1Builder::init()
    ->quantity(1)
    ->unitPrice('unitPrice4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

