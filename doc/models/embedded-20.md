
# Embedded 20

Payment Instrument Resources.

*This model accepts additional fields of type array.*

## Structure

`Embedded20`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `paymentInstruments` | [`?(PaymentInstruments12[])`](../../doc/models/payment-instruments-12.md) | Optional, Read-only | - | getPaymentInstruments(): ?array | setPaymentInstruments(?array paymentInstruments): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Embedded20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstruments12Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;

$embedded20 = Embedded20Builder::init()
    ->paymentInstruments(
        [
            PaymentInstruments12Builder::init()
                ->links(
                    Links20Builder::init()
                        ->self(
                            Self19Builder::init()
                                ->href('href0')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->customer(
                            Self18Builder::init()
                                ->href('href2')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                )
                ->id('id8')
                ->object('object4')
                ->default(false)
                ->state('state6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PaymentInstruments12Builder::init()
                ->links(
                    Links20Builder::init()
                        ->self(
                            Self19Builder::init()
                                ->href('href0')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->customer(
                            Self18Builder::init()
                                ->href('href2')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                )
                ->id('id8')
                ->object('object4')
                ->default(false)
                ->state('state6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            PaymentInstruments12Builder::init()
                ->links(
                    Links20Builder::init()
                        ->self(
                            Self19Builder::init()
                                ->href('href0')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->customer(
                            Self18Builder::init()
                                ->href('href2')
                                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                                ->build()
                        )
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                )
                ->id('id8')
                ->object('object4')
                ->default(false)
                ->state('state6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

