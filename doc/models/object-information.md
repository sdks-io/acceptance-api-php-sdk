
# Object Information

*This model accepts additional fields of type array.*

## Structure

`ObjectInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `title` | `?string` | Optional | Name or title of the customer.<br><br>**Constraints**: *Maximum Length*: `60` | getTitle(): ?string | setTitle(?string title): void |
| `comment` | `?string` | Optional | Comments that you can make about the customer.<br><br>**Constraints**: *Maximum Length*: `150` | getComment(): ?string | setComment(?string comment): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ObjectInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$objectInformation = ObjectInformationBuilder::init()
    ->title('title0')
    ->comment('comment8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

