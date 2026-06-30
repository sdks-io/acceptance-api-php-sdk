
# Payment Information 23

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation23`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eWallet` | [`?EWallet10`](../../doc/models/e-wallet-10.md) | Optional | - | getEWallet(): ?EWallet10 | setEWallet(?EWallet10 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation23Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentInformation23 = PaymentInformation23Builder::init()
    ->eWallet(
        EWallet10Builder::init()
            ->fundingSource('fundingSource2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

