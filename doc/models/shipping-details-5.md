
# Shipping Details 5

*This model accepts additional fields of type array.*

## Structure

`ShippingDetails5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `shippingMethod` | `?string` | Optional | Shipping method for the product. Possible values:<br><br>- `lowcost`: Lowest-cost service<br>- `sameday`: Courier or same-day service<br>- `oneday`: Next-day or overnight service<br>- `twoday`: Two-day service<br>- `threeday`: Three-day service<br>- `pickup`: Store pick-up<br>- `other`: Other shipping method<br>- `none`: No shipping method because product is a service or subscription<br><br>**Constraints**: *Maximum Length*: `32` | getShippingMethod(): ?string | setShippingMethod(?string shippingMethod): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shippingDetails5 = ShippingDetails5Builder::init()
    ->shippingMethod('shippingMethod2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

