
# Detail

*This model accepts additional fields of type array.*

## Structure

`Detail`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `field` | `?string` | Optional | This is the flattened JSON object field name/path that is either missing or invalid. | getField(): ?string | setField(?string field): void |
| `reason` | `?string` | Optional | Possible reasons for the error.<br><br>Possible values:<br><br>- MISSING_FIELD<br>- INVALID_DATA | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DetailBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$detail = DetailBuilder::init()
    ->field('field0')
    ->reason('reason8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

