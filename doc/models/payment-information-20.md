
# Payment Information 20

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType1`](../../doc/models/payment-type-1.md) | Optional | - | getPaymentType(): ?PaymentType1 | setPaymentType(?PaymentType1 paymentType): void |
| `eWallet` | [`?EWallet7`](../../doc/models/e-wallet-7.md) | Optional | - | getEWallet(): ?EWallet7 | setEWallet(?EWallet7 eWallet): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet7Builder;

$paymentInformation20 = PaymentInformation20Builder::init()
    ->paymentType(
        PaymentType1Builder::init()
            ->method(
                Method1Builder::init()
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->eWallet(
        EWallet7Builder::init()
            ->accountId('accountId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

