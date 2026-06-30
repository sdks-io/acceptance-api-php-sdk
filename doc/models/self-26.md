
# Self 26

*This model accepts additional fields of type array.*

## Structure

`Self26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the Customers Shipping Address | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Self26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$self26 = Self26Builder::init()
    ->href('/tms/v2/customers/D9F340DD3DB9C276E053A2598D0A41A3/shipping-addresses/D9F3439F0448C901E053A2598D0AA1CC')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

