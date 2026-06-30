
# Get Customer Shipping Address Response

*This model accepts additional fields of type array.*

## Structure

`GetCustomerShippingAddressResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `links` | [`?Links27`](../../doc/models/links-27.md) | Optional, Read-only | - | getLinks(): ?Links27 | setLinks(?Links27 links): void |
| `id` | `?string` | Optional | The Id of the Shipping Address Token.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `default` | `?bool` | Optional | Flag that indicates whether customer shipping address is the dafault.<br>Possible Values:<br><br>- `true`: Shipping Address is customer's default.<br>- `false`: Shipping Address is not customer's default. | getDefault(): ?bool | setDefault(?bool default): void |
| `shipTo` | [`?ShipTo14`](../../doc/models/ship-to-14.md) | Optional | - | getShipTo(): ?ShipTo14 | setShipTo(?ShipTo14 shipTo): void |
| `metadata` | [`?Metadata4`](../../doc/models/metadata-4.md) | Optional, Read-only | - | getMetadata(): ?Metadata4 | setMetadata(?Metadata4 metadata): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\GetCustomerShippingAddressResponseBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Links27Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Self26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer15Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ShipTo14Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Metadata4Builder;

$getCustomerShippingAddressResponse = GetCustomerShippingAddressResponseBuilder::init()
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
    ->id('id0')
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
    ->build();
```

