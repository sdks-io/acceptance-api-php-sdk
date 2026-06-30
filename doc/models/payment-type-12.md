
# Payment Type 12

*This model accepts additional fields of type array.*

## Structure

`PaymentType12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `method` | [`?Method12`](../../doc/models/method-12.md) | Optional | - | getMethod(): ?Method12 | setMethod(?Method12 method): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentType12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Method12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$paymentType12 = PaymentType12Builder::init()
    ->method(
        Method12Builder::init()
            ->type('type4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

