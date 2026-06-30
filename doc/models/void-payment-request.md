
# Void Payment Request

*This model accepts additional fields of type array.*

## Structure

`VoidPaymentRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation4`](../../doc/models/client-reference-information-4.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation4 | setClientReferenceInformation(?ClientReferenceInformation4 clientReferenceInformation): void |
| `paymentInformation` | [`?PaymentInformation9`](../../doc/models/payment-information-9.md) | Optional | - | getPaymentInformation(): ?PaymentInformation9 | setPaymentInformation(?PaymentInformation9 paymentInformation): void |
| `orderInformation` | [`?OrderInformation14`](../../doc/models/order-information-14.md) | Optional | - | getOrderInformation(): ?OrderInformation14 | setOrderInformation(?OrderInformation14 orderInformation): void |
| `agreementInformation` | [`?AgreementInformation1`](../../doc/models/agreement-information-1.md) | Optional | - | getAgreementInformation(): ?AgreementInformation1 | setAgreementInformation(?AgreementInformation1 agreementInformation): void |
| `merchantInformation` | [`?MerchantInformation7`](../../doc/models/merchant-information-7.md) | Optional | - | getMerchantInformation(): ?MerchantInformation7 | setMerchantInformation(?MerchantInformation7 merchantInformation): void |
| `processingInformation` | [`?ProcessingInformation13`](../../doc/models/processing-information-13.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation13 | setProcessingInformation(?ProcessingInformation13 processingInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\VoidPaymentRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Partner2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation7Builder;

$voidPaymentRequest = VoidPaymentRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation4Builder::init()
            ->code('code4')
            ->pausedRequestId('pausedRequestId2')
            ->comments('comments2')
            ->partner(
                Partner2Builder::init()
                    ->developerId('developerId0')
                    ->solutionId('solutionId2')
                    ->thirdPartyCertificationNumber('thirdPartyCertificationNumber6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->applicationName('applicationName2')
            ->transactionId('')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentInformation(
        PaymentInformation9Builder::init()
            ->paymentType(
                PaymentType3Builder::init()
                    ->name('name6')
                    ->subTypeName('subTypeName0')
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
        OrderInformation14Builder::init()
            ->amountDetails(
                AmountDetails5Builder::init()
                    ->totalAmount('totalAmount4')
                    ->currency('currency0')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->agreementInformation(
        AgreementInformation1Builder::init()
            ->agreementId('agreementId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation7Builder::init()
            ->transactionLocalDateTime('transactionLocalDateTime4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

