
# Options

*This model accepts additional fields of type array.*

## Structure

`Options`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Payment option ID name.<br>This is the bank’s swift code.Include the option ID name returned in the Options service response.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `60` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$options = OptionsBuilder::init()
    ->id('id2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

