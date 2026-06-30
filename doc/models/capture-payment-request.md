
# Capture Payment Request

*This model accepts additional fields of type array.*

## Structure

`CapturePaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation5`](../../doc/models/processing-information-5.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation5 | setProcessingInformation(?ProcessingInformation5 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation4`](../../doc/models/payment-information-4.md) | Optional | - | getPaymentInformation(): ?PaymentInformation4 | setPaymentInformation(?PaymentInformation4 paymentInformation): void |
| `orderInformation` | [`?OrderInformation6`](../../doc/models/order-information-6.md) | Optional | - | getOrderInformation(): ?OrderInformation6 | setOrderInformation(?OrderInformation6 orderInformation): void |
| `buyerInformation` | [`?BuyerInformation2`](../../doc/models/buyer-information-2.md) | Optional | - | getBuyerInformation(): ?BuyerInformation2 | setBuyerInformation(?BuyerInformation2 buyerInformation): void |
| `deviceInformation` | [`?DeviceInformation1`](../../doc/models/device-information-1.md) | Optional | - | getDeviceInformation(): ?DeviceInformation1 | setDeviceInformation(?DeviceInformation1 deviceInformation): void |
| `merchantInformation` | [`?MerchantInformation3`](../../doc/models/merchant-information-3.md) | Optional | - | getMerchantInformation(): ?MerchantInformation3 | setMerchantInformation(?MerchantInformation3 merchantInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation1`](../../doc/models/aggregator-information-1.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation1 | setAggregatorInformation(?AggregatorInformation1 aggregatorInformation): void |
| `pointOfSaleInformation` | [`?PointOfSaleInformation6`](../../doc/models/point-of-sale-information-6.md) | Optional | - | getPointOfSaleInformation(): ?PointOfSaleInformation6 | setPointOfSaleInformation(?PointOfSaleInformation6 pointOfSaleInformation): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation[])`](../../doc/models/merchant-defined-information.md) | Optional | The object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `merchantDefinedSecureInformation` | [`?MerchantDefinedSecureInformation2`](../../doc/models/merchant-defined-secure-information-2.md) | Optional | - | getMerchantDefinedSecureInformation(): ?MerchantDefinedSecureInformation2 | setMerchantDefinedSecureInformation(?MerchantDefinedSecureInformation2 merchantDefinedSecureInformation): void |
| `installmentInformation` | [`?InstallmentInformation2`](../../doc/models/installment-information-2.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation2 | setInstallmentInformation(?InstallmentInformation2 installmentInformation): void |
| `travelInformation` | [`?TravelInformation`](../../doc/models/travel-information.md) | Optional | - | getTravelInformation(): ?TravelInformation | setTravelInformation(?TravelInformation travelInformation): void |
| `promotionInformation` | [`?PromotionInformation`](../../doc/models/promotion-information.md) | Optional | - | getPromotionInformation(): ?PromotionInformation | setPromotionInformation(?PromotionInformation promotionInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CapturePaymentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CompanyBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BuyerInformation2Builder;

$capturePaymentRequest = CapturePaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('TC50171_3')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation5Builder::init()
            ->paymentSolution('paymentSolution6')
            ->reconciliationId('reconciliationId4')
            ->linkId('linkId8')
            ->reportGroup('reportGroup4')
            ->visaCheckoutId('visaCheckoutId6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation4Builder::init()
            ->customer(
                CustomerBuilder::init()
                    ->customerId('customerId4')
                    ->id('id0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->card(
                Card3Builder::init()
                    ->sourceAccountType('sourceAccountType0')
                    ->sourceAccountTypeDetails('sourceAccountTypeDetails0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->paymentType(
                PaymentType2Builder::init()
                    ->method(
                        Method2Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation6Builder::init()
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
                    LineItem3Builder::init()
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

