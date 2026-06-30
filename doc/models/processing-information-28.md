
# Processing Information 28

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation28`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `authorizationOptions` | [`?TmsAuthorizationOptions`](../../doc/models/tms-authorization-options.md) | Optional | - | getAuthorizationOptions(): ?TmsAuthorizationOptions | setAuthorizationOptions(?TmsAuthorizationOptions authorizationOptions): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation28Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TmsAuthorizationOptionsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransaction1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation28 = ProcessingInformation28Builder::init()
    ->authorizationOptions(
        TmsAuthorizationOptionsBuilder::init()
            ->initiator(
                Initiator2Builder::init()
                    ->merchantInitiatedTransaction(
                        MerchantInitiatedTransaction1Builder::init()
                            ->previousTransactionId('previousTransactionId8')
                            ->originalAuthorizedAmount('originalAuthorizedAmount2')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

