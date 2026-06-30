
# Shipping Address 1

*This model accepts additional fields of type array.*

## Structure

`ShippingAddress1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `default` | `?bool` | Optional | Flag that specifies if the Shipping Address should be made the Customers default.<br>Possible values:<br><br>- true<br>- false : (default)<br><br>**Default**: `false` | getDefault(): ?bool | setDefault(?bool default): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shippingAddress1 = ShippingAddress1Builder::init()
    ->default(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

