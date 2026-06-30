
# Payment Information 18

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation18`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eWallet` | [`?EWallet6`](../../doc/models/e-wallet-6.md) | Optional | - | getEWallet(): ?EWallet6 | setEWallet(?EWallet6 eWallet): void |
| `bank` | [`?Bank9`](../../doc/models/bank-9.md) | Optional | - | getBank(): ?Bank9 | setBank(?Bank9 bank): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation18Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\EWallet6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank9Builder;

$paymentInformation18 = PaymentInformation18Builder::init()
    ->eWallet(
        EWallet6Builder::init()
            ->accountId('accountId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->bank(
        Bank9Builder::init()
            ->iban('iban2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

