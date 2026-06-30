
# Customer 14

*This model accepts additional fields of type array.*

## Structure

`Customer14`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the Customer. | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Customer14Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$customer14 = Customer14Builder::init()
    ->href('/tms/v2/customers/D9F340DD3DB9C276E053A2598D0A41A3')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

