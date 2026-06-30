
# Detail 15

*This model accepts additional fields of type array.*

## Structure

`Detail15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `?string` | Optional | This is the flattened JSON object field name/path that is either missing or invalid. | getField(): ?string | setField(?string field): void |
| `message` | `?string` | Optional | The detailed message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$detail15 = Detail15Builder::init()
    ->field('field8')
    ->message('message4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

