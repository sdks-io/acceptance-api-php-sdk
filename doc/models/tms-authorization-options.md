
# Tms Authorization Options

*This model accepts additional fields of type array.*

## Structure

`TmsAuthorizationOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `initiator` | [`?Initiator2`](../../doc/models/initiator-2.md) | Optional | - | getInitiator(): ?Initiator2 | setInitiator(?Initiator2 initiator): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TmsAuthorizationOptionsBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransaction1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tmsAuthorizationOptions = TmsAuthorizationOptionsBuilder::init()
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
    ->build();
```

