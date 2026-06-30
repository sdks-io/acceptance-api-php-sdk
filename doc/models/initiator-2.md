
# Initiator 2

*This model accepts additional fields of type array.*

## Structure

`Initiator2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `merchantInitiatedTransaction` | [`?MerchantInitiatedTransaction1`](../../doc/models/merchant-initiated-transaction-1.md) | Optional | - | getMerchantInitiatedTransaction(): ?MerchantInitiatedTransaction1 | setMerchantInitiatedTransaction(?MerchantInitiatedTransaction1 merchantInitiatedTransaction): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Initiator2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MerchantInitiatedTransaction1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$initiator2 = Initiator2Builder::init()
    ->merchantInitiatedTransaction(
        MerchantInitiatedTransaction1Builder::init()
            ->previousTransactionId('previousTransactionId8')
            ->originalAuthorizedAmount('originalAuthorizedAmount2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

