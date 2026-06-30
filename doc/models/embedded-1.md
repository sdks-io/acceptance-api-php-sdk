
# Embedded 1

Additional resources for the Payment Instrument.

*This model accepts additional fields of type array.*

## Structure

`Embedded1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `instrumentIdentifier` | [`?TmsEmbeddedInstrumentIdentifier`](../../doc/models/tms-embedded-instrument-identifier.md) | Optional, Read-only | - | getInstrumentIdentifier(): ?TmsEmbeddedInstrumentIdentifier | setInstrumentIdentifier(?TmsEmbeddedInstrumentIdentifier instrumentIdentifier): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Embedded1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TmsEmbeddedInstrumentIdentifierBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links21Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self20Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInstruments1Builder;

$embedded1 = Embedded1Builder::init()
    ->instrumentIdentifier(
        TmsEmbeddedInstrumentIdentifierBuilder::init()
            ->links(
                Links21Builder::init()
                    ->self(
                        Self20Builder::init()
                            ->href('href0')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->paymentInstruments(
                        PaymentInstruments1Builder::init()
                            ->href('href0')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->id('id4')
            ->object('object2')
            ->state('state0')
            ->type('type6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

