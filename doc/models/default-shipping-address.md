
# Default Shipping Address

*This model accepts additional fields of type array.*

## Structure

`DefaultShippingAddress`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The Id of the Customers default Shipping Address | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DefaultShippingAddressBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$defaultShippingAddress = DefaultShippingAddressBuilder::init()
    ->id('id8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

