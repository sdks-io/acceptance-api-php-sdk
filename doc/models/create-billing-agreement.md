
# Create Billing Agreement

*This model accepts additional fields of type array.*

## Structure

`CreateBillingAgreement`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agreementInformation` | [`?AgreementInformation6`](../../doc/models/agreement-information-6.md) | Optional | - | getAgreementInformation(): ?AgreementInformation6 | setAgreementInformation(?AgreementInformation6 agreementInformation): void |
| `clientReferenceInformation` | [`?ClientReferenceInformation28`](../../doc/models/client-reference-information-28.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation28 | setClientReferenceInformation(?ClientReferenceInformation28 clientReferenceInformation): void |
| `aggregatorInformation` | [`?AggregatorInformation5`](../../doc/models/aggregator-information-5.md) | Optional | - | getAggregatorInformation(): ?AggregatorInformation5 | setAggregatorInformation(?AggregatorInformation5 aggregatorInformation): void |
| `consumerAuthenticationInformation` | [`?ConsumerAuthenticationInformation2`](../../doc/models/consumer-authentication-information-2.md) | Optional | - | getConsumerAuthenticationInformation(): ?ConsumerAuthenticationInformation2 | setConsumerAuthenticationInformation(?ConsumerAuthenticationInformation2 consumerAuthenticationInformation): void |
| `deviceInformation` | [`?DeviceInformation5`](../../doc/models/device-information-5.md) | Optional | - | getDeviceInformation(): ?DeviceInformation5 | setDeviceInformation(?DeviceInformation5 deviceInformation): void |
| `installmentInformation` | [`?InstallmentInformation4`](../../doc/models/installment-information-4.md) | Optional | - | getInstallmentInformation(): ?InstallmentInformation4 | setInstallmentInformation(?InstallmentInformation4 installmentInformation): void |
| `merchantInformation` | [`?MerchantInformation11`](../../doc/models/merchant-information-11.md) | Optional | - | getMerchantInformation(): ?MerchantInformation11 | setMerchantInformation(?MerchantInformation11 merchantInformation): void |
| `orderInformation` | [`?OrderInformation20`](../../doc/models/order-information-20.md) | Optional | - | getOrderInformation(): ?OrderInformation20 | setOrderInformation(?OrderInformation20 orderInformation): void |
| `paymentInformation` | [`?PaymentInformation16`](../../doc/models/payment-information-16.md) | Optional | - | getPaymentInformation(): ?PaymentInformation16 | setPaymentInformation(?PaymentInformation16 paymentInformation): void |
| `processingInformation` | [`?ProcessingInformation19`](../../doc/models/processing-information-19.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation19 | setProcessingInformation(?ProcessingInformation19 processingInformation): void |
| `buyerInformation` | [`?BuyerInformation6`](../../doc/models/buyer-information-6.md) | Optional | - | getBuyerInformation(): ?BuyerInformation6 | setBuyerInformation(?BuyerInformation6 buyerInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CreateBillingAgreementBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AggregatorInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\SubMerchantBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ConsumerAuthenticationInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation5Builder;

$createBillingAgreement = CreateBillingAgreementBuilder::init()
    ->agreementInformation(
        AgreementInformation6Builder::init()
            ->id('id2')
            ->dateSigned('dateSigned2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->clientReferenceInformation(
        ClientReferenceInformation28Builder::init()
            ->code('code4')
            ->reconciliationId('reconciliationId2')
            ->pausedRequestId('pausedRequestId2')
            ->transactionId('transactionId6')
            ->comments('comments2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->aggregatorInformation(
        AggregatorInformation5Builder::init()
            ->name('name0')
            ->subMerchant(
                SubMerchantBuilder::init()
                    ->cardAcceptorId('cardAcceptorId0')
                    ->id('id6')
                    ->name('name6')
                    ->address1('address16')
                    ->locality('locality4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->consumerAuthenticationInformation(
        ConsumerAuthenticationInformation2Builder::init()
            ->authenticationTransactionContextId('authenticationTransactionContextId4')
            ->cavv('cavv2')
            ->transactionToken('transactionToken0')
            ->xid('xid4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->deviceInformation(
        DeviceInformation5Builder::init()
            ->httpAcceptBrowserValue('httpAcceptBrowserValue6')
            ->ipAddress('ipAddress6')
            ->userAgentBrowserValue('userAgentBrowserValue6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

