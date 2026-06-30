
# Last

*This model accepts additional fields of type array.*

## Structure

`Last`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `href` | `?string` | Optional, Read-only | Link to the last page. | getHref(): ?string | setHref(?string href): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LastBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$last = LastBuilder::init()
    ->href('/tms/v2/customers/D9F340DD3DB9C276E053A2598D0A41A3/shipping-addresses?offset=0&limit=1')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

