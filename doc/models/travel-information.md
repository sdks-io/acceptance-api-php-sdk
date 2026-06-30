
# Travel Information

*This model accepts additional fields of type array.*

## Structure

`TravelInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `duration` | `?string` | Optional | Duration of the auto rental or lodging rental.<br><br>#### Auto rental<br><br>This field is supported for Visa, MasterCard, and American Express.<br>**Important** If this field is not included when the `processingInformation.industryDataType` is auto rental,<br>the transaction is declined.<br><br>**Constraints**: *Maximum Length*: `2` | getDuration(): ?string | setDuration(?string duration): void |
| `agency` | [`?Agency`](../../doc/models/agency.md) | Optional | - | getAgency(): ?Agency | setAgency(?Agency agency): void |
| `autoRental` | [`?AutoRental`](../../doc/models/auto-rental.md) | Optional | - | getAutoRental(): ?AutoRental | setAutoRental(?AutoRental autoRental): void |
| `lodging` | [`?Lodging`](../../doc/models/lodging.md) | Optional | - | getLodging(): ?Lodging | setLodging(?Lodging lodging): void |
| `transit` | [`?Transit`](../../doc/models/transit.md) | Optional | - | getTransit(): ?Transit | setTransit(?Transit transit): void |
| `vehicleData` | [`?VehicleData`](../../doc/models/vehicle-data.md) | Optional | - | getVehicleData(): ?VehicleData | setVehicleData(?VehicleData vehicleData): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AgencyBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\AutoRentalBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\LodgingBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RoomBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TransitBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AirlineBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TicketIssuerBuilder;

$travelInformation = TravelInformationBuilder::init()
    ->duration('duration8')
    ->agency(
        AgencyBuilder::init()
            ->code('code4')
            ->name('name6')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->autoRental(
        AutoRentalBuilder::init()
            ->noShowIndicator(false)
            ->customerName('customerName0')
            ->vehicleClass('vehicleClass4')
            ->distanceTravelled('distanceTravelled6')
            ->distanceUnit('distanceUnit0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->lodging(
        LodgingBuilder::init()
            ->checkInDate('checkInDate0')
            ->checkOutDate('checkOutDate2')
            ->room(
                [
                    RoomBuilder::init()
                        ->dailyRate('dailyRate0')
                        ->numberOfNights(138)
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build(),
                    RoomBuilder::init()
                        ->dailyRate('dailyRate0')
                        ->numberOfNights(138)
                        ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                        ->build()
                ]
            )
            ->smokingPreference('smokingPreference2')
            ->numberOfRooms(16)
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->transit(
        TransitBuilder::init()
            ->airline(
                AirlineBuilder::init()
                    ->isDomestic('isDomestic8')
                    ->bookingReferenceNumber('bookingReferenceNumber6')
                    ->carrierName('carrierName0')
                    ->ticketIssuer(
                        TicketIssuerBuilder::init()
                            ->code('code2')
                            ->name('name4')
                            ->address('address0')
                            ->locality('locality6')
                            ->administrativeArea('administrativeArea0')
                            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                            ->build()
                    )
                    ->ticketNumber('ticketNumber4')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

