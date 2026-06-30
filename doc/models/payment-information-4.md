
# Payment Information 4

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customer` | [`?Customer`](../../doc/models/customer.md) | Optional | - | getCustomer(): ?Customer | setCustomer(?Customer customer): void |
| `card` | [`?Card3`](../../doc/models/card-3.md) | Optional | - | getCard(): ?Card3 | setCard(?Card3 card): void |
| `paymentType` | [`?PaymentType2`](../../doc/models/payment-type-2.md) | Optional | - | getPaymentType(): ?PaymentType2 | setPaymentType(?PaymentType2 paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\CustomerBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Card3Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;

$paymentInformation4 = PaymentInformation4Builder::init()
    ->customer(
        CustomerBuilder::init()
            ->customerId('customerId4')
            ->id('id0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->card(
        Card3Builder::init()
            ->sourceAccountType('sourceAccountType0')
            ->sourceAccountTypeDetails('sourceAccountTypeDetails0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentType(
        PaymentType2Builder::init()
            ->method(
                Method2Builder::init()
                    ->name('name6')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

