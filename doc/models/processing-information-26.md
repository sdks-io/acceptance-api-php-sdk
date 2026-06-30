
# Processing Information 26

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation26`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the void to invoke bundled services along with void.<br>Possible values:<br><br>- `AP_UPDATE_ORDER`: Use this when Alternative Payment Update order service is requested.<br>- `AP_EXTEND_ORDER`: Use this when Alternative Payment extend order service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation26Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation26 = ProcessingInformation26Builder::init()
    ->actionList(
        [
            'actionList5',
            'actionList6',
            'actionList7'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

