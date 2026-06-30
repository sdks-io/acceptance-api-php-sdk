
# Travel Information 8

*This model accepts additional fields of type array.*

## Structure

`TravelInformation8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `agency` | [`?Agency5`](../../doc/models/agency-5.md) | Optional | - | getAgency(): ?Agency5 | setAgency(?Agency5 agency): void |
| `journeyType` | `?string` | Optional | The type of journey. | getJourneyType(): ?string | setJourneyType(?string journeyType): void |
| `actualFinalDestination` | `?string` | Optional | The actual final destination of the travel. | getActualFinalDestination(): ?string | setActualFinalDestination(?string actualFinalDestination): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelInformation8Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Agency5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$travelInformation8 = TravelInformation8Builder::init()
    ->agency(
        Agency5Builder::init()
            ->startDate('startDate4')
            ->endDate('endDate8')
            ->changeOfGuest('changeOfGuest6')
            ->countryCode('countryCode8')
            ->locality('locality6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->journeyType('journeyType4')
    ->actualFinalDestination('actualFinalDestination6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

