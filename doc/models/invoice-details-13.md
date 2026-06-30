
# Invoice Details 13

*This model accepts additional fields of type array.*

## Structure

`InvoiceDetails13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `barcodeNumber` | `?string` | Optional | Barcode ID scanned from the Payment Application.<br><br>**Constraints**: *Maximum Length*: `100` | getBarcodeNumber(): ?string | setBarcodeNumber(?string barcodeNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoiceDetails13 = InvoiceDetails13Builder::init()
    ->barcodeNumber('barcodeNumber0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

