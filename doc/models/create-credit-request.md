
# Create Credit Request

*This model accepts additional fields of type array.*

## Structure

`CreateCreditRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation11`](../../doc/models/processing-information-11.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation11 | setProcessingInformation(?ProcessingInformation11 processingInformation): void |
| `paymentInformation` | [`?PaymentInformation5`](../../doc/models/payment-information-5.md) | Optional | - | getPaymentInformation(): ?PaymentInformation5 | setPaymentInformation(?PaymentInformation5 paymentInformation): void |
| `orderInformation` | [`?OrderInformation8`](../../doc/models/order-information-8.md) | Optional | - | getOrderInformation(): ?OrderInformation8 | setOrderInformation(?OrderInformation8 orderInformation): void |
| `buyerInformation` | [`?BuyerInformation2`](../../doc/models/buyer-information-2.md) | Optional | - | getBuyerInformation(): ?BuyerInformation2 | setBuyerInformation(?BuyerInformation2 buyerInformation): void |
| `deviceInformation` | [`?DeviceInformation1`](../../doc/models/device-information-1.md) | Optional | - | getDeviceInformation(): ?DeviceInformation1 | setDeviceInformation(?DeviceInformation1 deviceInformation): void |
| `merchantInformation` | [`?MerchantInformation4`](../../doc/models/merchant-information-4.md) | Optional | - | getMerchantInformation(): ?MerchantInformation4 | setMerchantInformation(?MerchantInformation4 merchantInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation1`](../../doc/models/aggregator-information-1.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation1 | setAggregatorInformation(?AggregatorInformation1 aggregatorInformation): void |
| `pointOfSaleInformation` | [`?PointOfSaleInformation`](../../doc/models/point-of-sale-information.md) | Optional | - | getPointOfSaleInformation(): ?PointOfSaleInformation | setPointOfSaleInformation(?PointOfSaleInformation pointOfSaleInformation): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation[])`](../../doc/models/merchant-defined-information.md) | Optional | The object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `merchantDefinedSecureInformation` | [`?MerchantDefinedSecureInformation2`](../../doc/models/merchant-defined-secure-information-2.md) | Optional | - | getMerchantDefinedSecureInformation(): ?MerchantDefinedSecureInformation2 | setMerchantDefinedSecureInformation(?MerchantDefinedSecureInformation2 merchantDefinedSecureInformation): void |
| `installmentInformation` | [`?InstallmentInformation3`](../../doc/models/installment-information-3.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation3 | setInstallmentInformation(?InstallmentInformation3 installmentInformation): void |
| `travelInformation` | [`?TravelInformation`](../../doc/models/travel-information.md) | Optional | - | getTravelInformation(): ?TravelInformation | setTravelInformation(?TravelInformation travelInformation): void |
| `recipientInformation` | [`?RecipientInformation1`](../../doc/models/recipient-information-1.md) | Optional | - | getRecipientInformation(): ?RecipientInformation1 | setRecipientInformation(?RecipientInformation1 recipientInformation): void |
| `senderInformation` | [`?SenderInformation1`](../../doc/models/sender-information-1.md) | Optional | - | getSenderInformation(): ?SenderInformation1 | setSenderInformation(?SenderInformation1 senderInformation): void |
| `promotionInformation` | [`?PromotionInformation`](../../doc/models/promotion-information.md) | Optional | - | getPromotionInformation(): ?PromotionInformation | setPromotionInformation(?PromotionInformation promotionInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CreateCreditRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation11Builder;
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

$createCreditRequest = CreateCreditRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformationBuilder::init()
            ->code('12345678')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation11Builder::init()
            ->commerceIndicator('commerceIndicator4')
            ->processorId('processorId2')
            ->paymentSolution('paymentSolution6')
            ->reconciliationId('reconciliationId4')
            ->linkId('linkId8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation5Builder::init()
            ->card(
                Card4Builder::init()
                    ->number('4111111111111111')
                    ->expirationMonth('03')
                    ->expirationYear('2031')
                    ->type('001')
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
                    ->totalAmount('200')
                    ->currency('usd')
                    ->discountAmount('discountAmount2')
                    ->dutyAmount('dutyAmount2')
                    ->gratuityAmount('gratuityAmount4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->billTo(
                BillTo2Builder::init()
                    ->title('title4')
                    ->firstName('Test')
                    ->middleName('middleName6')
                    ->lastName('test')
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
                    ->address1('test')
                    ->locality('Ann Arbor')
                    ->administrativeArea('MI')
                    ->postalCode('48104-2201')
                    ->country('US')
                    ->email('test@cybs.com')
                    ->phoneNumber('9999999999')
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

