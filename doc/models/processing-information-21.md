
# Processing Information 21

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation21`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the order to invoke bundled services along with order.<br>Possible values:<br><br>- `AP_ORDER`: Use this when Alternative Payment Order service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation21Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation21 = ProcessingInformation21Builder::init()
    ->actionList(
        [
            'actionList3',
            'actionList4'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

