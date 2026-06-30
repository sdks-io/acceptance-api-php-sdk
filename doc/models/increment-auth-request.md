
# Increment Auth Request

*This model accepts additional fields of type array.*

## Structure

`IncrementAuthRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `clientReferenceInformation` | [`?ClientReferenceInformation2`](../../doc/models/client-reference-information-2.md) | Optional | - | getClientReferenceInformation(): ?ClientReferenceInformation2 | setClientReferenceInformation(?ClientReferenceInformation2 clientReferenceInformation): void |
| `processingInformation` | [`?ProcessingInformation2`](../../doc/models/processing-information-2.md) | Optional | - | getProcessingInformation(): ?ProcessingInformation2 | setProcessingInformation(?ProcessingInformation2 processingInformation): void |
| `orderInformation` | [`?OrderInformation2`](../../doc/models/order-information-2.md) | Optional | - | getOrderInformation(): ?OrderInformation2 | setOrderInformation(?OrderInformation2 orderInformation): void |
| `merchantInformation` | [`?MerchantInformation2`](../../doc/models/merchant-information-2.md) | Optional | - | getMerchantInformation(): ?MerchantInformation2 | setMerchantInformation(?MerchantInformation2 merchantInformation): void |
| `travelInformation` | [`?TravelInformation1`](../../doc/models/travel-information-1.md) | Optional | - | getTravelInformation(): ?TravelInformation1 | setTravelInformation(?TravelInformation1 travelInformation): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IncrementAuthRequestBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ClientReferenceInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Partner1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrderInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelInformation1Builder;

$incrementAuthRequest = IncrementAuthRequestBuilder::init()
    ->clientReferenceInformation(
        ClientReferenceInformation2Builder::init()
            ->code('TC50171_3')
            ->partner(
                Partner1Builder::init()
                    ->originalTransactionId('originalTransactionId0')
                    ->developerId('developerId0')
                    ->solutionId('solutionId2')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->applicationName('applicationName2')
            ->applicationVersion('applicationVersion6')
            ->applicationUser('applicationUser8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->processingInformation(
        ProcessingInformation2Builder::init()
            ->authorizationOptions(
                AuthorizationOptions3Builder::init()
                    ->initiator(
                        Initiator1Builder::init()
                            ->storedCredentialUsed(true)
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
        OrderInformation2Builder::init()
            ->amountDetails(
                AmountDetails3Builder::init()
                    ->additionalAmount('22.49')
                    ->currency('USD')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->merchantInformation(
        MerchantInformation2Builder::init()
            ->transactionLocalDateTime('20191002080000')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->travelInformation(
        TravelInformation1Builder::init()
            ->duration('4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

