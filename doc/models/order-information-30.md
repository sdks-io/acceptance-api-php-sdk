
# Order Information 30

*This model accepts additional fields of type array.*

## Structure

`OrderInformation30`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails32`](../../doc/models/amount-details-32.md) | Optional | - | getAmountDetails(): ?AmountDetails32 | setAmountDetails(?AmountDetails32 amountDetails): void |
| `billTo` | [`?BillTo14`](../../doc/models/bill-to-14.md) | Optional | - | getBillTo(): ?BillTo14 | setBillTo(?BillTo14 billTo): void |
| `shipTo` | [`?ShipTo11`](../../doc/models/ship-to-11.md) | Optional | - | getShipTo(): ?ShipTo11 | setShipTo(?ShipTo11 shipTo): void |
| `lineItems` | [`?(LineItem9[])`](../../doc/models/line-item-9.md) | Optional | **Constraints**: *Maximum Items*: `10` | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `invoiceDetails` | [`?InvoiceDetails14`](../../doc/models/invoice-details-14.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails14 | setInvoiceDetails(?InvoiceDetails14 invoiceDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation30Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails32Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails14Builder;

$orderInformation30 = OrderInformation30Builder::init()
    ->amountDetails(
        AmountDetails32Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->discountAmount('discountAmount2')
            ->shippingAmount('shippingAmount6')
            ->shippingDiscountAmount('shippingDiscountAmount0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillTo14Builder::init()
            ->email('email8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipTo11Builder::init()
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
            LineItem9Builder::init()
                ->productName('productName8')
                ->productDescription('productDescription0')
                ->productSku('productSku8')
                ->quantity(132)
                ->typeOfSupply('typeOfSupply8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            LineItem9Builder::init()
                ->productName('productName8')
                ->productDescription('productDescription0')
                ->productSku('productSku8')
                ->quantity(132)
                ->typeOfSupply('typeOfSupply8')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->invoiceDetails(
        InvoiceDetails14Builder::init()
            ->productDescription('productDescription6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

