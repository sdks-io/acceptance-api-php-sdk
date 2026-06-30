
# Travel

*This model accepts additional fields of type array.*

## Structure

`Travel`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `actualFinalDestination` | [`?ActualFinalDestination`](../../doc/models/actual-final-destination.md) | Optional | - | getActualFinalDestination(): ?ActualFinalDestination | setActualFinalDestination(?ActualFinalDestination actualFinalDestination): void |
| `firstDeparture` | [`?FirstDeparture`](../../doc/models/first-departure.md) | Optional | - | getFirstDeparture(): ?FirstDeparture | setFirstDeparture(?FirstDeparture firstDeparture): void |
| `firstDestination` | [`?FirstDestination`](../../doc/models/first-destination.md) | Optional | - | getFirstDestination(): ?FirstDestination | setFirstDestination(?FirstDestination firstDestination): void |
| `lastDestination` | [`?LastDestination`](../../doc/models/last-destination.md) | Optional | - | getLastDestination(): ?LastDestination | setLastDestination(?LastDestination lastDestination): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ActualFinalDestinationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstDepartureBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstDestinationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LastDestinationBuilder;

$travel = TravelBuilder::init()
    ->actualFinalDestination(
        ActualFinalDestinationBuilder::init()
            ->country('country6')
            ->locality('locality2')
            ->latitude('latitude4')
            ->longitude('longitude6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->firstDeparture(
        FirstDepartureBuilder::init()
            ->country('country2')
            ->locality('locality8')
            ->latitude('latitude2')
            ->longitude('longitude2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->firstDestination(
        FirstDestinationBuilder::init()
            ->country('country6')
            ->locality('locality2')
            ->latitude('latitude4')
            ->longitude('longitude6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lastDestination(
        LastDestinationBuilder::init()
            ->country('country4')
            ->locality('locality0')
            ->latitude('latitude4')
            ->longitude('longitude4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

