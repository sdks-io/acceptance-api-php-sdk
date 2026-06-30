
# Create Order Request

*This model accepts additional fields of type array.*

## Structure

`CreateOrderRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation39`](../../doc/models/client-reference-information-39.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation39 | setClientReferenceInformation(?ClientReferenceInformation39 clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation25`](../../doc/models/processing-information-25.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation25 | setProcessingInformation(?ProcessingInformation25 processingInformation): void |
| `merchantInformation` | [`?MerchantInformation16`](../../doc/models/merchant-information-16.md) | Optional | - | getMerchantInformation(): ?MerchantInformation16 | setMerchantInformation(?MerchantInformation16 merchantInformation): void |
| `paymentInformation` | [`?PaymentInformation26`](../../doc/models/payment-information-26.md) | Optional | - | getPaymentInformation(): ?PaymentInformation26 | setPaymentInformation(?PaymentInformation26 paymentInformation): void |
| `orderInformation` | [`?OrderInformation30`](../../doc/models/order-information-30.md) | Optional | - | getOrderInformation(): ?OrderInformation30 | setOrderInformation(?OrderInformation30 orderInformation): void |
| `senderInformation` | [`?SenderInformation2`](../../doc/models/sender-information-2.md) | Optional | - | getSenderInformation(): ?SenderInformation2 | setSenderInformation(?SenderInformation2 senderInformation): void |
| `eventInformation` | [`?EventInformation`](../../doc/models/event-information.md) | Optional | - | getEventInformation(): ?EventInformation | setEventInformation(?EventInformation eventInformation): void |
| `travelInformation` | [`?TravelInformation8`](../../doc/models/travel-information-8.md) | Optional | - | getTravelInformation(): ?TravelInformation8 | setTravelInformation(?TravelInformation8 travelInformation): void |
| `recipientInformation` | [`?RecipientInformation2`](../../doc/models/recipient-information-2.md) | Optional | - | getRecipientInformation(): ?RecipientInformation2 | setRecipientInformation(?RecipientInformation2 recipientInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CreateOrderRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation39Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation25Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantDescriptor11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method19Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet13Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation30Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails32Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\BillTo14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LineItem9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\InvoiceDetails14Builder;

$createOrderRequest = CreateOrderRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation39Builder::init()
            ->reconciliationId('reconciliationId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation25Builder::init()
            ->processingInstruction('processingInstruction8')
            ->authorizationOptions(
                AuthorizationOptions5Builder::init()
                    ->authType('authType2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->highRiskTransactionFlag('highRiskTransactionFlag2')
            ->transactionRetry('transactionRetry8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation16Builder::init()
            ->merchantDescriptor(
                MerchantDescriptor11Builder::init()
                    ->name('name2')
                    ->email('email4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->cancelUrl('cancelUrl8')
            ->successUrl('successUrl6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation26Builder::init()
            ->paymentType(
                PaymentType19Builder::init()
                    ->name('name6')
                    ->method(
                        Method19Builder::init()
                            ->name('name6')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->tokenizedPaymentMethod(
                TokenizedPaymentMethod2Builder::init()
                    ->description('description0')
                    ->usagePattern('usagePattern8')
                    ->usageType('usageType0')
                    ->allowMultipleTokens(false)
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->industryType('industryType6')
            ->eWallet(
                EWallet13Builder::init()
                    ->accountId('accountId4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orderInformation(
        OrderInformation30Builder::init()
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
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

