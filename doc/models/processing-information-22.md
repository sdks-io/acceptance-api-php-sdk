
# Processing Information 22

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation22`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `intentsId` | `?string` | Optional | Set to the value of the requestID field returned in the order service response.<br><br>**Constraints**: *Maximum Length*: `26` | getIntentsId(): ?string | setIntentsId(?string intentsId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation22Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation22 = ProcessingInformation22Builder::init()
    ->intentsId('intentsId2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

