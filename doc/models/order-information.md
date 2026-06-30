
# Order Information

*This model accepts additional fields of type array.*

## Structure

`OrderInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails`](../../doc/models/amount-details.md) | Optional | - | getAmountDetails(): ?AmountDetails | setAmountDetails(?AmountDetails amountDetails): void |
| `billTo` | [`?BillTo`](../../doc/models/bill-to.md) | Optional | - | getBillTo(): ?BillTo | setBillTo(?BillTo billTo): void |
| `shipTo` | [`?ShipTo`](../../doc/models/ship-to.md) | Optional | - | getShipTo(): ?ShipTo | setShipTo(?ShipTo shipTo): void |
| `lineItems` | [`?(LineItem[])`](../../doc/models/line-item.md) | Optional | - | getLineItems(): ?array | setLineItems(?array lineItems): void |
| `invoiceDetails` | [`?InvoiceDetails`](../../doc/models/invoice-details.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails | setInvoiceDetails(?InvoiceDetails invoiceDetails): void |
| `shippingDetails` | [`?ShippingDetails2`](../../doc/models/shipping-details-2.md) | Optional | - | getShippingDetails(): ?ShippingDetails2 | setShippingDetails(?ShippingDetails2 shippingDetails): void |
| `returnsAccepted` | `?bool` | Optional | This is only needed when you are requesting both payment and DM service at same time.<br><br>Boolean that indicates whether returns are accepted for this order.<br>This field can contain one of the following values:<br><br>- true: Returns are accepted for this order.<br>- false: Returns are not accepted for this order. | getReturnsAccepted(): ?bool | setReturnsAccepted(?bool returnsAccepted): void |
| `isCryptocurrencyPurchase` | `?string` | Optional | #### Visa Platform Connect :<br><br>This API will contain the Flag that specifies whether the payment is for the purchase of cryptocurrency.<br>Additional values to add :<br>This API will contain the Flag that specifies whether the payment is for the purchase of cryptocurrency.<br>valid values are<br><br>- Y/y, true<br>- N/n, false | getIsCryptocurrencyPurchase(): ?string | setIsCryptocurrencyPurchase(?string isCryptocurrencyPurchase): void |
| `cutoffDateTime` | `?string` | Optional | Starting date and time for an event or a journey that is independent of which transportation mechanism, in UTC. The cutoffDateTime will supersede travelInformation.transit.airline.legs[].departureDate and travelInformation.transit.airline.legs[].departureTime if these fields are supplied in the request.<br>Format: YYYY-MM-DDThh:mm:ssZ. Example 2016-08-11T22:47:57Z equals August 11, 2016, at 22:47:57 (10:47:57 p.m.). The T separates the date and the time. The Z indicates UTC. | getCutoffDateTime(): ?string | setCutoffDateTime(?string cutoffDateTime): void |
| `preOrder` | `?string` | Optional | Indicates whether cardholder is placing an order with a future availability or release date.<br>This field can contain one of these values:<br><br>- MERCHANDISE_AVAILABLE: Merchandise available<br>- FUTURE_AVAILABILITY: Future availability | getPreOrder(): ?string | setPreOrder(?string preOrder): void |
| `preOrderDate` | `?string` | Optional | Expected date that a pre-ordered purchase will be available. Format: YYYYMMDD<br><br>**Constraints**: *Maximum Length*: `10` | getPreOrderDate(): ?string | setPreOrderDate(?string preOrderDate): void |
| `reordered` | `?bool` | Optional | Indicates whether the cardholder is reordering previously purchased merchandise.<br>This field can contain one of these values:<br><br>- false: First time ordered<br>- true: Reordered | getReordered(): ?bool | setReordered(?bool reordered): void |
| `totalOffersCount` | `?string` | Optional | Total number of articles/items in the order as a numeric decimal count.<br>Possible values: 00 - 99<br><br>**Constraints**: *Maximum Length*: `2` | getTotalOffersCount(): ?string | setTotalOffersCount(?string totalOffersCount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetailsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillToBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipToBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItemBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetailsBuilder;

$orderInformation = OrderInformationBuilder::init()
    ->amountDetails(
        AmountDetailsBuilder::init()
            ->giftWrapAmount('giftWrapAmount6')
            ->invoiceAmount('invoiceAmount2')
            ->totalAmount('totalAmount4')
            ->subTotalAmount('subTotalAmount0')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->billTo(
        BillToBuilder::init()
            ->firstName('firstName4')
            ->lastName('lastName2')
            ->middleName('middleName6')
            ->nameSuffix('nameSuffix8')
            ->title('title4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->shipTo(
        ShipToBuilder::init()
            ->title('title0')
            ->firstName('firstName0')
            ->middleName('middleName2')
            ->lastName('lastName8')
            ->address1('address12')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lineItems(
        [
            LineItemBuilder::init()
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
        InvoiceDetailsBuilder::init()
            ->invoiceNumber('invoiceNumber8')
            ->barcodeNumber('barcodeNumber8')
            ->expirationDate('expirationDate2')
            ->purchaseOrderNumber('purchaseOrderNumber8')
            ->purchaseOrderDate('purchaseOrderDate4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

