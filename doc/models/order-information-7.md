
# Order Information 7

*This model accepts additional fields of type array.*

## Structure

`OrderInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails10`](../../doc/models/amount-details-10.md) | Optional | - | getAmountDetails(): ?AmountDetails10 | setAmountDetails(?AmountDetails10 amountDetails): void |
| `invoiceDetails` | [`?InvoiceDetails5`](../../doc/models/invoice-details-5.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails5 | setInvoiceDetails(?InvoiceDetails5 invoiceDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails5Builder;

$orderInformation7 = OrderInformation7Builder::init()
    ->amountDetails(
        AmountDetails10Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->processorTransactionFee('processorTransactionFee0')
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

