
# Processing Information 13

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actionList` | `?(string[])` | Optional | Array of actions (one or more) to be included in the void to invoke bundled services along with void.<br>Possible values:<br><br>- `AP_CANCEL`: Use this when Alternative Payment Void service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation13 = ProcessingInformation13Builder::init()
    ->actionList(
        [
            'actionList9',
            'actionList0',
            'actionList1'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

