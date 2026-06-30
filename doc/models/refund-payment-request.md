
# Refund Payment Request

*This model accepts additional fields of type array.*

## Structure

`RefundPaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation10`](../../doc/models/client-reference-information-10.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation10 | setClientReferenceInformation(?ClientReferenceInformation10 clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation7`](../../doc/models/processing-information-7.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation7 | setProcessingInformation(?ProcessingInformation7 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation5`](../../doc/models/payment-information-5.md) | Optional | - | getPaymentInformation(): ?PaymentInformation5 | setPaymentInformation(?PaymentInformation5 paymentInformation): void |
| `orderInformation` | [`?OrderInformation8`](../../doc/models/order-information-8.md) | Optional | - | getOrderInformation(): ?OrderInformation8 | setOrderInformation(?OrderInformation8 orderInformation): void |
| `buyerInformation` | [`?BuyerInformation2`](../../doc/models/buyer-information-2.md) | Optional | - | getBuyerInformation(): ?BuyerInformation2 | setBuyerInformation(?BuyerInformation2 buyerInformation): void |
| `deviceInformation` | [`?DeviceInformation1`](../../doc/models/device-information-1.md) | Optional | - | getDeviceInformation(): ?DeviceInformation1 | setDeviceInformation(?DeviceInformation1 deviceInformation): void |
| `merchantInformation` | [`?MerchantInformation4`](../../doc/models/merchant-information-4.md) | Optional | - | getMerchantInformation(): ?MerchantInformation4 | setMerchantInformation(?MerchantInformation4 merchantInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation1`](../../doc/models/aggregator-information-1.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation1 | setAggregatorInformation(?AggregatorInformation1 aggregatorInformation): void |
| `pointOfSaleInformation` | [`?PointOfSaleInformation8`](../../doc/models/point-of-sale-information-8.md) | Optional | - | getPointOfSaleInformation(): ?PointOfSaleInformation8 | setPointOfSaleInformation(?PointOfSaleInformation8 pointOfSaleInformation): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation[])`](../../doc/models/merchant-defined-information.md) | Optional | The object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `travelInformation` | [`?TravelInformation`](../../doc/models/travel-information.md) | Optional | - | getTravelInformation(): ?TravelInformation | setTravelInformation(?TravelInformation travelInformation): void |
| `promotionInformation` | [`?PromotionInformation`](../../doc/models/promotion-information.md) | Optional | - | getPromotionInformation(): ?PromotionInformation | setPromotionInformation(?PromotionInformation promotionInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RefundPaymentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCardBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\FluidDataBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CompanyBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation2Builder;

$refundPaymentRequest = RefundPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation10Builder::init()
            ->code('Testing-VDP-Payments-Refund')
            ->reconciliationId('reconciliationId2')
            ->returnReconciliationId('returnReconciliationId8')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation7Builder::init()
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->paymentSolution('paymentSolution6')
            ->reconciliationId('reconciliationId4')
            ->linkId('linkId8')
            ->reportGroup('reportGroup4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation5Builder::init()
            ->card(
                Card4Builder::init()
                    ->number('number6')
                    ->expirationMonth('expirationMonth4')
                    ->expirationYear('expirationYear0')
                    ->type('type4')
                    ->accountEncoderId('accountEncoderId8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->bank(
                Bank2Builder::init()
                    ->account(
                        Account3Builder::init()
                            ->type('type0')
                            ->number('number8')
                            ->encoderId('encoderId4')
                            ->checkNumber('checkNumber6')
                            ->checkImageReferenceNumber('checkImageReferenceNumber2')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->routingNumber('routingNumber0')
                    ->iban('iban2')
                    ->swiftCode('swiftCode0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->tokenizedCard(
                TokenizedCardBuilder::init()
                    ->number('number2')
                    ->expirationMonth('expirationMonth0')
                    ->expirationYear('expirationYear4')
                    ->type('type0')
                    ->cryptogram('cryptogram0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->fluidData(
                FluidDataBuilder::init()
                    ->keySerialNumber('keySerialNumber4')
                    ->descriptor('descriptor0')
                    ->value('value0')
                    ->encoding('encoding0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->customer(
                CustomerBuilder::init()
                    ->customerId('customerId4')
                    ->id('id0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation8Builder::init()
            ->amountDetails(
                AmountDetails9Builder::init()
                    ->totalAmount('102.21')
                    ->currency('USD')
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
            ->build()
    )
    ->buyerInformation(
        BuyerInformation2Builder::init()
            ->merchantCustomerId('merchantCustomerId4')
            ->vatRegistrationNumber('vatRegistrationNumber0')
            ->dateOfBirth('dateOfBirth2')
            ->gender('gender6')
            ->language('language2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

