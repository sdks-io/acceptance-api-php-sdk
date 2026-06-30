
# Order Information 8

*This model accepts additional fields of type array.*

## Structure

`OrderInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails9`](../../doc/models/amount-details-9.md) | Optional | - | getAmountDetails(): ?AmountDetails9 | setAmountDetails(?AmountDetails9 amountDetails): void |
| `billTo` | [`?BillTo2`](../../doc/models/bill-to-2.md) | Optional | - | getBillTo(): ?BillTo2 | setBillTo(?BillTo2 billTo): void |
| `shipTo` | [`?ShipTo2`](../../doc/models/ship-to-2.md) | Optional | - | getShipTo(): ?ShipTo2 | setShipTo(?ShipTo2 shipTo): void |
| `lineItems` | [`?(LineItem4[])`](../../doc/models/line-item-4.md) | Optional | - | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `invoiceDetails` | [`?InvoiceDetails4`](../../doc/models/invoice-details-4.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails4 | setInvoiceDetails(?InvoiceDetails4 invoiceDetails): void |
| `shippingDetails` | [`?ShippingDetails1`](../../doc/models/shipping-details-1.md) | Optional | - | getShippingDetails(): ?ShippingDetails1 | setShippingDetails(?ShippingDetails1 shippingDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CompanyBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails4Builder;

$orderInformation8 = OrderInformation8Builder::init()
    ->amountDetails(
        AmountDetails9Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->discountAmount('discountAmount2')
            ->dutyAmount('dutyAmount2')
            ->gratuityAmount('gratuityAmount4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillTo2Builder::init()
            ->title('title4')
            ->firstName('firstName4')
            ->middleName('middleName6')
            ->lastName('lastName2')
            ->company(
                CompanyBuilder::init()
                    ->name('name0')
                    ->address1('address18')
                    ->address2('address22')
                    ->locality('locality0')
                    ->administrativeArea('administrativeArea6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo2Builder::init()
            ->administrativeArea('administrativeArea0')
            ->country('country8')
            ->postalCode('postalCode6')
            ->email('email2')
            ->county('county8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lineItems(
        [
            LineItem4Builder::init()
                ->productCode('productCode4')
                ->productName('productName8')
                ->productSku('productSku8')
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            LineItem4Builder::init()
                ->productCode('productCode4')
                ->productName('productName8')
                ->productSku('productSku8')
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            LineItem4Builder::init()
                ->productCode('productCode4')
                ->productName('productName8')
                ->productSku('productSku8')
                ->quantity(132)
                ->unitPrice('unitPrice8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->invoiceDetails(
        InvoiceDetails4Builder::init()
            ->purchaseOrderNumber('purchaseOrderNumber8')
            ->purchaseOrderDate('purchaseOrderDate4')
            ->purchaseContactName('purchaseContactName4')
            ->taxable(false)
            ->vatInvoiceReferenceNumber('vatInvoiceReferenceNumber4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

