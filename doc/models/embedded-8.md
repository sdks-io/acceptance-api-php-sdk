
# Embedded 8

*This model accepts additional fields of type array.*

## Structure

`Embedded8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `shippingAddresses` | [`?(ShippingAddress16[])`](../../doc/models/shipping-address-16.md) | Optional, Read-only | - | getShippingAddresses(): ?array | setShippingAddresses(?array shippingAddresses): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Embedded8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress16Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer15Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata4Builder;

$embedded8 = Embedded8Builder::init()
    ->shippingAddresses(
        [
            ShippingAddress16Builder::init()
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
                ->id('id4')
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
                ->build(),
            ShippingAddress16Builder::init()
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
                ->id('id4')
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
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

