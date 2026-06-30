
# Order Information 9

*This model accepts additional fields of type array.*

## Structure

`OrderInformation9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails12`](../../doc/models/amount-details-12.md) | Optional | - | getAmountDetails(): ?AmountDetails12 | setAmountDetails(?AmountDetails12 amountDetails): void |
| `invoiceDetails` | [`?InvoiceDetails5`](../../doc/models/invoice-details-5.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails5 | setInvoiceDetails(?InvoiceDetails5 invoiceDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails5Builder;

$orderInformation9 = OrderInformation9Builder::init()
    ->amountDetails(
        AmountDetails12Builder::init()
            ->settlementAmount('settlementAmount0')
            ->settlementCurrency('settlementCurrency8')
            ->exchangeRate('exchangeRate6')
            ->foreignAmount('foreignAmount8')
            ->foreignCurrency('foreignCurrency2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->invoiceDetails(
        InvoiceDetails5Builder::init()
            ->level3TransmissionStatus(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

