
# Invoice Details 3

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `productId` | `?string` | Optional | Product identifier code. Also known as the Stock Keeping Unit (SKU) code for the product.<br><br>**Constraints**: *Maximum Length*: `35` | getProductId(): ?string | setProductId(?string productId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails3 = InvoiceDetails3Builder::init()
    ->productId('productId8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

