
# Invoice Details 14

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `productDescription` | `?string` | Optional | Brief description of item. | getProductDescription(): ?string | setProductDescription(?string productDescription): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails14 = InvoiceDetails14Builder::init()
    ->productDescription('productDescription2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

