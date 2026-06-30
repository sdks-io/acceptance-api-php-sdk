
# Payment Information 22

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `card` | [`?Card10`](../../doc/models/card-10.md) | Optional | - | getCard(): ?Card10 | setCard(?Card10 card): void |
| `bank` | [`?Bank11`](../../doc/models/bank-11.md) | Optional | - | getBank(): ?Bank11 | setBank(?Bank11 bank): void |
| `eWallet` | [`?EWallet9`](../../doc/models/e-wallet-9.md) | Optional | - | getEWallet(): ?EWallet9 | setEWallet(?EWallet9 eWallet): void |
| `options` | [`?Options1`](../../doc/models/options-1.md) | Optional | - | getOptions(): ?Options1 | setOptions(?Options1 options): void |
| `paymentType` | [`?PaymentType`](../../doc/models/payment-type.md) | Optional | - | getPaymentType(): ?PaymentType | setPaymentType(?PaymentType paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation22Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet9Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Options1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentTypeBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\MethodBuilder;

$paymentInformation22 = PaymentInformation22Builder::init()
    ->card(
        Card10Builder::init()
            ->number('number6')
            ->expirationMonth('expirationMonth4')
            ->expirationYear('expirationYear0')
            ->type('type4')
            ->securityCode('securityCode2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank11Builder::init()
            ->swiftCode('swiftCode0')
            ->account(
                Account12Builder::init()
                    ->number('number8')
                    ->iban('iban4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->eWallet(
        EWallet9Builder::init()
            ->fundingSource('fundingSource2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->options(
        Options1Builder::init()
            ->id('id2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentType(
        PaymentTypeBuilder::init()
            ->name('name6')
            ->subTypeName('subTypeName0')
            ->method(
                MethodBuilder::init()
                    ->name('name6')
                    ->type('type4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

