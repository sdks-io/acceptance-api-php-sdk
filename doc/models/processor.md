
# Processor

*This model accepts additional fields of type array.*

## Structure

`Processor`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the Processor.<br><br>**Constraints**: *Maximum Length*: `30` | getName(): ?string | setName(?string name): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processor = ProcessorBuilder::init()
    ->name('name0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

