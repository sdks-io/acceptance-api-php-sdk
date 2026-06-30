
# Refresh Payment Status Request

*This model accepts additional fields of type array.*

## Structure

`RefreshPaymentStatusRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInformation` | [`?PaymentInformation14`](../../doc/models/payment-information-14.md) | Optional | - | getPaymentInformation(): ?PaymentInformation14 | setPaymentInformation(?PaymentInformation14 paymentInformation): void |
| `clientReferenceInformation` | [`?ClientReferenceInformation26`](../../doc/models/client-reference-information-26.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation26 | setClientReferenceInformation(?ClientReferenceInformation26 clientReferenceInformation): void |
| `agreementInformation` | [`?AgreementInformation5`](../../doc/models/agreement-information-5.md) | Optional | - | getAgreementInformation(): ?AgreementInformation5 | setAgreementInformation(?AgreementInformation5 agreementInformation): void |
| `processingInformation` | [`?ProcessingInformation18`](../../doc/models/processing-information-18.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation18 | setProcessingInformation(?ProcessingInformation18 processingInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RefreshPaymentStatusRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AgreementInformation5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation18Builder;

$refreshPaymentStatusRequest = RefreshPaymentStatusRequestBuilder::init()
    ->paymentInformation(
        PaymentInformation14Builder::init()
            ->customer(
                Customer10Builder::init()
                    ->customerId('customerId4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->paymentType(
                PaymentType11Builder::init()
                    ->name('name6')
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
    ->clientReferenceInformation(
        ClientReferenceInformation26Builder::init()
            ->code('code4')
            ->reconciliationId('reconciliationId2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->agreementInformation(
        AgreementInformation5Builder::init()
            ->agreementId('agreementId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation18Builder::init()
            ->actionList(
                [
                    'actionList3',
                    'actionList4'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

