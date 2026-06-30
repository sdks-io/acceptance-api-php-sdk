
# Payment Information 21

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eWallet` | [`?EWallet8`](../../doc/models/e-wallet-8.md) | Optional | - | getEWallet(): ?EWallet8 | setEWallet(?EWallet8 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation21Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation21 = PaymentInformation21Builder::init()
    ->eWallet(
        EWallet8Builder::init()
            ->accountId('accountId4')
            ->fundingSource('fundingSource2')
            ->fundingSourceSale('fundingSourceSale0')
            ->userName('userName6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

