
# Shipping Address 4

*This model accepts additional fields of type array.*

## Structure

`ShippingAddress4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Unique identifier for the Customers Shipping Address token that was created as part of a bundled TOKEN_CREATE action.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `32` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ShippingAddress4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$shippingAddress4 = ShippingAddress4Builder::init()
    ->id('id4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

