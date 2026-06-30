
# Payment Information 15

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentType` | [`?PaymentType12`](../../doc/models/payment-type-12.md) | Optional | - | getPaymentType(): ?PaymentType12 | setPaymentType(?PaymentType12 paymentType): void |
| `eWallet` | [`?EWallet5`](../../doc/models/e-wallet-5.md) | Optional | - | getEWallet(): ?EWallet5 | setEWallet(?EWallet5 eWallet): void |
| `customer` | [`?Customer10`](../../doc/models/customer-10.md) | Optional | - | getCustomer(): ?Customer10 | setCustomer(?Customer10 customer): void |
| `bank` | [`?Bank6`](../../doc/models/bank-6.md) | Optional | - | getBank(): ?Bank6 | setBank(?Bank6 bank): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation15Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer10Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account8Builder;

$paymentInformation15 = PaymentInformation15Builder::init()
    ->paymentType(
        PaymentType12Builder::init()
            ->method(
                Method12Builder::init()
                    ->type('type4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->eWallet(
        EWallet5Builder::init()
            ->name('name4')
            ->fundingSource('fundingSource2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->customer(
        Customer10Builder::init()
            ->customerId('customerId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank6Builder::init()
            ->account(
                Account8Builder::init()
                    ->ibanSuffix('ibanSuffix8')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

