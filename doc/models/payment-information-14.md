
# Payment Information 14

*This model accepts additional fields of type array.*

## Structure

`PaymentInformation14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `customer` | [`?Customer10`](../../doc/models/customer-10.md) | Optional | - | getCustomer(): ?Customer10 | setCustomer(?Customer10 customer): void |
| `paymentType` | [`?PaymentType11`](../../doc/models/payment-type-11.md) | Optional | - | getPaymentType(): ?PaymentType11 | setPaymentType(?PaymentType11 paymentType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInformation14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer10Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method2Builder;

$paymentInformation14 = PaymentInformation14Builder::init()
    ->customer(
        Customer10Builder::init()
            ->customerId('customerId4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->paymentType(
        PaymentType11Builder::init()
            ->name('name6')
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

