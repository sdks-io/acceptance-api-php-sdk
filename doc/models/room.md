
# Room

*This model accepts additional fields of type array.*

## Structure

`Room`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `dailyRate` | `?string` | Optional | Daily cost of the room.<br><br>**Constraints**: *Maximum Length*: `8` | getDailyRate(): ?string | setDailyRate(?string dailyRate): void |
| `numberOfNights` | `?int` | Optional | Number of nights billed at the rate specified by `travelInformation.lodging.room[].dailyRate`.<br><br>**Constraints**: `>= 1`, `<= 9999` | getNumberOfNights(): ?int | setNumberOfNights(?int numberOfNights): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RoomBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$room = RoomBuilder::init()
    ->dailyRate('dailyRate0')
    ->numberOfNights(138)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

