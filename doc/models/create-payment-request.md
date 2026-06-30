
# Create Payment Request

*This model accepts additional fields of type array.*

## Structure

`CreatePaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation`](../../doc/models/client-reference-information.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation | setClientReferenceInformation(?ClientReferenceInformation clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation`](../../doc/models/processing-information.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation | setProcessingInformation(?ProcessingInformation processingInformation): void |
| `issuerInformation` | [`?IssuerInformation`](../../doc/models/issuer-information.md) | Optional | - | getIssuerInformation(): ?IssuerInformation | setIssuerInformation(?IssuerInformation issuerInformation): void |
| `paymentInformation` | [`?PaymentInformation`](../../doc/models/payment-information.md) | Optional | - | getPaymentInformation(): ?PaymentInformation | setPaymentInformation(?PaymentInformation paymentInformation): void |
| `orderInformation` | [`?OrderInformation`](../../doc/models/order-information.md) | Optional | - | getOrderInformation(): ?OrderInformation | setOrderInformation(?OrderInformation orderInformation): void |
| `buyerInformation` | [`?BuyerInformation`](../../doc/models/buyer-information.md) | Optional | - | getBuyerInformation(): ?BuyerInformation | setBuyerInformation(?BuyerInformation buyerInformation): void |
| `senderInformation` | [`?SenderInformation`](../../doc/models/sender-information.md) | Optional | - | getSenderInformation(): ?SenderInformation | setSenderInformation(?SenderInformation senderInformation): void |
| `recipientInformation` | [`?RecipientInformation`](../../doc/models/recipient-information.md) | Optional | - | getRecipientInformation(): ?RecipientInformation | setRecipientInformation(?RecipientInformation recipientInformation): void |
| `deviceInformation` | [`?DeviceInformation`](../../doc/models/device-information.md) | Optional | - | getDeviceInformation(): ?DeviceInformation | setDeviceInformation(?DeviceInformation deviceInformation): void |
| `merchantInformation` | [`?MerchantInformation`](../../doc/models/merchant-information.md) | Optional | - | getMerchantInformation(): ?MerchantInformation | setMerchantInformation(?MerchantInformation merchantInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation`](../../doc/models/aggregator-information.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation | setAggregatorInformation(?AggregatorInformation aggregatorInformation): void |
| `consumerAuthenticationInformation` | [`?ConsumerAuthenticationInformation`](../../doc/models/consumer-authentication-information.md) | Optional | - | getConsumerAuthenticationInformation(): ?ConsumerAuthenticationInformation | setConsumerAuthenticationInformation(?ConsumerAuthenticationInformation consumerAuthenticationInformation): void |
| `pointOfSaleInformation` | [`?PointOfSaleInformation`](../../doc/models/point-of-sale-information.md) | Optional | - | getPointOfSaleInformation(): ?PointOfSaleInformation | setPointOfSaleInformation(?PointOfSaleInformation pointOfSaleInformation): void |
| `merchantDefinedInformation` | [`?(MerchantDefinedInformation[])`](../../doc/models/merchant-defined-information.md) | Optional | The object containing the custom data that the merchant defines. | getMerchantDefinedInformation(): ?array | setMerchantDefinedInformation(?array merchantDefinedInformation): void |
| `merchantDefinedSecureInformation` | [`?MerchantDefinedSecureInformation2`](../../doc/models/merchant-defined-secure-information-2.md) | Optional | - | getMerchantDefinedSecureInformation(): ?MerchantDefinedSecureInformation2 | setMerchantDefinedSecureInformation(?MerchantDefinedSecureInformation2 merchantDefinedSecureInformation): void |
| `installmentInformation` | [`?InstallmentInformation`](../../doc/models/installment-information.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation | setInstallmentInformation(?InstallmentInformation installmentInformation): void |
| `travelInformation` | [`?TravelInformation`](../../doc/models/travel-information.md) | Optional | - | getTravelInformation(): ?TravelInformation | setTravelInformation(?TravelInformation travelInformation): void |
| `healthCareInformation` | [`?HealthCareInformation`](../../doc/models/health-care-information.md) | Optional | - | getHealthCareInformation(): ?HealthCareInformation | setHealthCareInformation(?HealthCareInformation healthCareInformation): void |
| `promotionInformation` | [`?PromotionInformation`](../../doc/models/promotion-information.md) | Optional | - | getPromotionInformation(): ?PromotionInformation | setPromotionInformation(?PromotionInformation promotionInformation): void |
| `tokenInformation` | [`?TokenInformation`](../../doc/models/token-information.md) | Optional | - | getTokenInformation(): ?TokenInformation | setTokenInformation(?TokenInformation tokenInformation): void |
| `invoiceDetails` | [`?InvoiceDetails13`](../../doc/models/invoice-details-13.md) | Optional | - | getInvoiceDetails(): ?InvoiceDetails13 | setInvoiceDetails(?InvoiceDetails13 invoiceDetails): void |
| `processorInformation` | [`?ProcessorInformation5`](../../doc/models/processor-information-5.md) | Optional | - | getProcessorInformation(): ?ProcessorInformation5 | setProcessorInformation(?ProcessorInformation5 processorInformation): void |
| `agreementInformation` | [`?AgreementInformation`](../../doc/models/agreement-information.md) | Optional | - | getAgreementInformation(): ?AgreementInformation | setAgreementInformation(?AgreementInformation agreementInformation): void |
| `riskInformation` | [`?RiskInformation3`](../../doc/models/risk-information-3.md) | Optional | - | getRiskInformation(): ?RiskInformation3 | setRiskInformation(?RiskInformation3 riskInformation): void |
| `acquirerInformation` | [`?AcquirerInformation`](../../doc/models/acquirer-information.md) | Optional | - | getAcquirerInformation(): ?AcquirerInformation | setAcquirerInformation(?AcquirerInformation acquirerInformation): void |
| `recurringPaymentInformation` | [`?RecurringPaymentInformation2`](../../doc/models/recurring-payment-information-2.md) | Optional | - | getRecurringPaymentInformation(): ?RecurringPaymentInformation2 | setRecurringPaymentInformation(?RecurringPaymentInformation2 recurringPaymentInformation): void |
| `unscheduledPaymentInformation` | [`?UnscheduledPaymentInformation`](../../doc/models/unscheduled-payment-information.md) | Optional | - | getUnscheduledPaymentInformation(): ?UnscheduledPaymentInformation | setUnscheduledPaymentInformation(?UnscheduledPaymentInformation unscheduledPaymentInformation): void |
| `hostedPaymentInformation` | [`?HostedPaymentInformation`](../../doc/models/hosted-payment-information.md) | Optional | - | getHostedPaymentInformation(): ?HostedPaymentInformation | setHostedPaymentInformation(?HostedPaymentInformation hostedPaymentInformation): void |
| `watchlistScreeningInformation` | [`?WatchlistScreeningInformation`](../../doc/models/watchlist-screening-information.md) | Optional | - | getWatchlistScreeningInformation(): ?WatchlistScreeningInformation | setWatchlistScreeningInformation(?WatchlistScreeningInformation watchlistScreeningInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CreatePaymentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CardBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedCardBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethodBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DirectDebitBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MandateBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\FluidDataBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetailsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillToBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipToBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItemBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetailsBuilder;

$createPaymentRequest = CreatePaymentRequestBuilder::init()
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
        ProcessingInformationBuilder::init()
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->enableEscrowOption(false)
            ->actionTokenTypes(
                [
                    'actionTokenTypes2',
                    'actionTokenTypes3'
                ]
            )
            ->binSource('binSource8')
            ->capture(false)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->issuerInformation(
        IssuerInformationBuilder::init()
            ->discretionaryData('discretionaryData8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformationBuilder::init()
            ->card(
                CardBuilder::init()
                    ->number('5555555555554444')
                    ->expirationMonth('12')
                    ->expirationYear('2031')
                    ->type('002')
                    ->useAs('useAs8')
                    ->securityCode('123')
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
            ->tokenizedPaymentMethod(
                TokenizedPaymentMethodBuilder::init()
                    ->id('id0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->directDebit(
                DirectDebitBuilder::init()
                    ->mandate(
                        MandateBuilder::init()
                            ->clearingDate('clearingDate6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
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
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformationBuilder::init()
            ->amountDetails(
                AmountDetailsBuilder::init()
                    ->giftWrapAmount('giftWrapAmount6')
                    ->invoiceAmount('invoiceAmount2')
                    ->totalAmount('102.21')
                    ->subTotalAmount('subTotalAmount0')
                    ->currency('USD')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->billTo(
                BillToBuilder::init()
                    ->firstName('RTS')
                    ->lastName('VDP')
                    ->middleName('middleName6')
                    ->nameSuffix('nameSuffix8')
                    ->title('title4')
                    ->address1('201 S. Division St.')
                    ->locality('Ann Arbor')
                    ->administrativeArea('MI')
                    ->postalCode('48104-2201')
                    ->country('US')
                    ->district('MI')
                    ->buildingNumber('123')
                    ->email('test@cybs.com')
                    ->phoneNumber('999999999')
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
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

