
# Payment Information 30

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation30`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `tokenizedPaymentMethod` | [`?TokenizedPaymentMethod4`](../../doc/models/tokenized-payment-method-4.md) | Optional | - | getTokenizedPaymentMethod(): ?TokenizedPaymentMethod4 | setTokenizedPaymentMethod(?TokenizedPaymentMethod4 tokenizedPaymentMethod): void |
| `eWallet` | [`?EWallet13`](../../doc/models/e-wallet-13.md) | Optional | - | getEWallet(): ?EWallet13 | setEWallet(?EWallet13 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation30Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet13Builder;

$paymentInformation30 = PaymentInformation30Builder::init()
    ->tokenizedPaymentMethod(
        TokenizedPaymentMethod4Builder::init()
            ->id('id0')
            ->usageType('usageType0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->eWallet(
        EWallet13Builder::init()
            ->accountId('accountId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

