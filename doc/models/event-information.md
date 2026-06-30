
# Event Information

*This model accepts additional fields of type array.*

## Structure

`EventInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `date` | `?string` | Optional | The date of the event. | getDate(): ?string | setDate(?string date): void |
| `type` | `?string` | Optional | The type of the event. | getType(): ?string | setType(?string type): void |
| `totalTickets` | `?string` | Optional | The total number of tickets for the event. | getTotalTickets(): ?string | setTotalTickets(?string totalTickets): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\EventInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$eventInformation = EventInformationBuilder::init()
    ->date('date4')
    ->type('type2')
    ->totalTickets('totalTickets2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

