
# Processing Information 23

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation23`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `sessionType` | `?string` | Optional | Will have 2 values, 'U' (Update) , 'N' (New). Any other values will be rejected. Default will be 'N'<br><br>**Constraints**: *Maximum Length*: `5` | getSessionType(): ?string | setSessionType(?string sessionType): void |
| `paymentFlowMode` | `?string` | Optional | Whether merchant wants to pass the flow Inline or want to invoke Klarna Hosted Page<br><br>**Constraints**: *Maximum Length*: `50` | getPaymentFlowMode(): ?string | setPaymentFlowMode(?string paymentFlowMode): void |
| `actionList` | `?(string[])` | Optional | Possible values are one or more of follows:<br><br>- `AP_SESSIONS`: Use this when Alternative Payment Sessions service is requested. | getActionList(): ?array | setActionList(?array actionList): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation23Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation23 = ProcessingInformation23Builder::init()
    ->sessionType('sessionType8')
    ->paymentFlowMode('paymentFlowMode6')
    ->actionList(
        [
            'actionList3',
            'actionList4'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

