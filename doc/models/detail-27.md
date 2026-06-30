
# Detail 27

*This model accepts additional fields of type array.*

## Structure

`Detail27`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Possible reasons for the error.<br><br>Possible values:<br><br>- MISSING_FIELD<br>- INVALID_DATA | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail27Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$detail27 = Detail27Builder::init()
    ->reason('reason4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

