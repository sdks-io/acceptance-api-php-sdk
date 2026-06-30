
# Invoice

*This model accepts additional fields of type array.*

## Structure

`Invoice`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | Invoice Number. | getNumber(): ?string | setNumber(?string number): void |
| `barcodeNumber` | `?string` | Optional | Barcode Number. | getBarcodeNumber(): ?string | setBarcodeNumber(?string barcodeNumber): void |
| `expirationDate` | `?string` | Optional | Expiration Date. | getExpirationDate(): ?string | setExpirationDate(?string expirationDate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$invoice = InvoiceBuilder::init()
    ->number('number6')
    ->barcodeNumber('barcodeNumber4')
    ->expirationDate('expirationDate0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

