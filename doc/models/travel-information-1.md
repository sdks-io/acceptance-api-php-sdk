
# Travel Information 1

*This model accepts additional fields of type array.*

## Structure

`TravelInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `duration` | `?string` | Optional | Duration for which the vehicle was rented or lodge/hotel was booked.<br><br>**Constraints**: *Maximum Length*: `2` | getDuration(): ?string | setDuration(?string duration): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$travelInformation1 = TravelInformation1Builder::init()
    ->duration('duration6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

