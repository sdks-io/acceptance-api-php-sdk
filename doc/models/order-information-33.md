
# Order Information 33

*This model accepts additional fields of type array.*

## Structure

`OrderInformation33`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `billTo` | [`?BillTo56`](../../doc/models/bill-to-56.md) | Optional | - | getBillTo(): ?BillTo56 | setBillTo(?BillTo56 billTo): void |
| `shipTo` | [`?ShipTo25`](../../doc/models/ship-to-25.md) | Optional | - | getShipTo(): ?ShipTo25 | setShipTo(?ShipTo25 shipTo): void |
| `lineItems` | [`?(LineItem11[])`](../../doc/models/line-item-11.md) | Optional | Transaction Line Item data. | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `amountDetails` | [`?AmountDetails35`](../../doc/models/amount-details-35.md) | Optional | - | getAmountDetails(): ?AmountDetails35 | setAmountDetails(?AmountDetails35 amountDetails): void |
| `shippingDetails` | [`?ShippingDetails8`](../../doc/models/shipping-details-8.md) | Optional | - | getShippingDetails(): ?ShippingDetails8 | setShippingDetails(?ShippingDetails8 shippingDetails): void |
| `invoiceDetails` | [`?InvoiceDetails16`](../../doc/models/invoice-details-16.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails16 | setInvoiceDetails(?InvoiceDetails16 invoiceDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation33Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo56Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails35Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingDetails8Builder;

$orderInformation33 = OrderInformation33Builder::init()
    ->billTo(
        BillTo56Builder::init()
            ->firstName('firstName4')
            ->lastName('lastName2')
            ->middleName('middleName6')
            ->nameSuffix('nameSuffix8')
            ->address1('address16')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo25Builder::init()
            ->firstName('firstName0')
            ->lastName('lastName8')
            ->address1('address12')
            ->address2('address26')
            ->locality('locality4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lineItems(
        [
            LineItem11Builder::init()
                ->productCode('productCode4')
                ->productName('productName8')
                ->productSku('productSku8')
                ->taxAmount('taxAmount6')
                ->quantity(132)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            LineItem11Builder::init()
                ->productCode('productCode4')
                ->productName('productName8')
                ->productSku('productSku8')
                ->taxAmount('taxAmount6')
                ->quantity(132)
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->amountDetails(
        AmountDetails35Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->taxAmount('taxAmount8')
            ->authorizedAmount('authorizedAmount0')
            ->settlementAmount('settlementAmount0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shippingDetails(
        ShippingDetails8Builder::init()
            ->giftWrap(false)
            ->shippingMethod('shippingMethod6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

