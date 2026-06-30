
# Embedded 4

*This model accepts additional fields of type array.*

## Structure

`Embedded4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `defaultPaymentInstrument` | [`?DefaultPaymentInstrument1`](../../doc/models/default-payment-instrument-1.md) | Optional, Read-only | - | getDefaultPaymentInstrument(): ?DefaultPaymentInstrument1 | setDefaultPaymentInstrument(?DefaultPaymentInstrument1 defaultPaymentInstrument): void |
| `defaultShippingAddress` | [`?DefaultShippingAddress1`](../../doc/models/default-shipping-address-1.md) | Optional, Read-only | - | getDefaultShippingAddress(): ?DefaultShippingAddress1 | setDefaultShippingAddress(?DefaultShippingAddress1 defaultShippingAddress): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Embedded4Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DefaultPaymentInstrument1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links20Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self19Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self18Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DefaultShippingAddress1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self26Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer15Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata4Builder;

$embedded4 = Embedded4Builder::init()
    ->defaultPaymentInstrument(
        DefaultPaymentInstrument1Builder::init()
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
            ->id('id4')
            ->object('object2')
            ->default(false)
            ->state('state0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->defaultShippingAddress(
        DefaultShippingAddress1Builder::init()
            ->links(
                Links27Builder::init()
                    ->self(
                        Self26Builder::init()
                            ->href('href0')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->customer(
                        Customer15Builder::init()
                            ->href('href2')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->id('id8')
            ->default(false)
            ->shipTo(
                ShipTo14Builder::init()
                    ->firstName('firstName0')
                    ->lastName('lastName8')
                    ->company('company4')
                    ->address1('address12')
                    ->address2('address26')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->metadata(
                Metadata4Builder::init()
                    ->creator('creator4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

