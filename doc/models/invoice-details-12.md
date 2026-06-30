
# Invoice Details 12

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `costCenter` | `?string` | Optional | Cost centre of the merchant. | getCostCenter(): ?string | setCostCenter(?string costCenter): void |
| `productDescription` | `?string` | Optional | Brief description of item. | getProductDescription(): ?string | setProductDescription(?string productDescription): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails12 = InvoiceDetails12Builder::init()
    ->costCenter('costCenter0')
    ->productDescription('productDescription0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

