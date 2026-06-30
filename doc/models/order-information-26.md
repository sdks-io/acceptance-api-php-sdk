
# Order Information 26

*This model accepts additional fields of type array.*

## Structure

`OrderInformation26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billTo` | [`?BillTo12`](../../doc/models/bill-to-12.md) | Optional | - | getBillTo(): ?BillTo12 | setBillTo(?BillTo12 billTo): void |
| `shipTo` | [`?ShipTo9`](../../doc/models/ship-to-9.md) | Optional | - | getShipTo(): ?ShipTo9 | setShipTo(?ShipTo9 shipTo): void |
| `amountDetails` | [`?AmountDetails28`](../../doc/models/amount-details-28.md) | Optional | - | getAmountDetails(): ?AmountDetails28 | setAmountDetails(?AmountDetails28 amountDetails): void |
| `lineItems` | [`?(LineItem7[])`](../../doc/models/line-item-7.md) | Optional | - | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `invoiceDetails` | [`?InvoiceDetails12`](../../doc/models/invoice-details-12.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails12 | setInvoiceDetails(?InvoiceDetails12 invoiceDetails): void |
| `shippingDetails` | [`?ShippingDetails5`](../../doc/models/shipping-details-5.md) | Optional | - | getShippingDetails(): ?ShippingDetails5 | setShippingDetails(?ShippingDetails5 shippingDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails12Builder;

$orderInformation26 = OrderInformation26Builder::init()
    ->billTo(
        BillTo12Builder::init()
            ->name('name8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo9Builder::init()
            ->email('email2')
            ->title('title0')
            ->firstName('firstName0')
            ->middleName('middleName2')
            ->lastName('lastName8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->amountDetails(
        AmountDetails28Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->discountAmount('discountAmount2')
            ->taxAmount('taxAmount8')
            ->dutyAmount('dutyAmount2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lineItems(
        [
            LineItem7Builder::init()
                ->productSku('productSku8')
                ->productName('productName8')
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->discountAmount('discountAmount4')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->invoiceDetails(
        InvoiceDetails12Builder::init()
            ->costCenter('costCenter6')
            ->productDescription('productDescription6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

