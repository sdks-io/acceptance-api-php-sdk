
# Order Information 3

*This model accepts additional fields of type array.*

## Structure

`OrderInformation3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails2`](../../doc/models/amount-details-2.md) | Optional | - | getAmountDetails(): ?AmountDetails2 | setAmountDetails(?AmountDetails2 amountDetails): void |
| `invoiceDetails` | [`?InvoiceDetails3`](../../doc/models/invoice-details-3.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails3 | setInvoiceDetails(?InvoiceDetails3 invoiceDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails3Builder;

$orderInformation3 = OrderInformation3Builder::init()
    ->amountDetails(
        AmountDetails2Builder::init()
            ->totalAmount('totalAmount4')
            ->authorizedAmount('authorizedAmount0')
            ->currency('currency0')
            ->settlementAmount('settlementAmount0')
            ->settlementCurrency('settlementCurrency8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->invoiceDetails(
        InvoiceDetails3Builder::init()
            ->productId('productId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

