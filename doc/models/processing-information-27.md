
# Processing Information 27

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation27`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the payment to invoke bundled services.<br>Possible values are one or more of follows:<br><br>- `TOKEN_RETRIEVE`: Use this when Alternative Payment token retrieval is requested.<br>- `TOKEN_DELETE`: Use this when Alternative Payment token deletion is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation27Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation27 = ProcessingInformation27Builder::init()
    ->actionList(
        [
            'actionList7',
            'actionList8',
            'actionList9'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

