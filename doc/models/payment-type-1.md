
# Payment Type 1

*This model accepts additional fields of type array.*

## Structure

`PaymentType1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`?Method1`](../../doc/models/method-1.md) | Optional | - | getMethod(): ?Method1 | setMethod(?Method1 method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType1 = PaymentType1Builder::init()
    ->method(
        Method1Builder::init()
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

