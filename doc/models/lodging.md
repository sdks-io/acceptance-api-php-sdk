
# Lodging

*This model accepts additional fields of type array.*

## Structure

`Lodging`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `checkInDate` | `?string` | Optional | Date on which the guest checked in. In the case of a no-show or a reservation, the scheduled arrival date.<br>Format: `MMDDYY`. For best interchange rates, make sure it is a valid date.<br><br>**Constraints**: *Maximum Length*: `6` | getCheckInDate(): ?string | setCheckInDate(?string checkInDate): void |
| `checkOutDate` | `?string` | Optional | Date on which the guest checked out.<br>Format: `MMDDYY`. For best interchange rates, make sure it is a valid date.<br><br>**Constraints**: *Maximum Length*: `6` | getCheckOutDate(): ?string | setCheckOutDate(?string checkOutDate): void |
| `room` | [`?(Room[])`](../../doc/models/room.md) | Optional | The object containing the number of nights and the daily rate that applies for that no of nights. | getRoom(): ?array | setRoom(?array room): void |
| `smokingPreference` | `?string` | Optional | Smoking preference of the guest.<br>Possible values:<br><br>- `Y`: smoking room<br>- `N`: non-smoking room<br><br>**Constraints**: *Maximum Length*: `1` | getSmokingPreference(): ?string | setSmokingPreference(?string smokingPreference): void |
| `numberOfRooms` | `?int` | Optional | Number of rooms booked by the cardholder.<br><br>**Constraints**: `>= 1`, `<= 99` | getNumberOfRooms(): ?int | setNumberOfRooms(?int numberOfRooms): void |
| `numberOfGuests` | `?int` | Optional | Number of guests staying in the room.<br><br>**Constraints**: `>= 1`, `<= 99` | getNumberOfGuests(): ?int | setNumberOfGuests(?int numberOfGuests): void |
| `roomBedType` | `?string` | Optional | Type of room, such as queen, king, or two doubles.<br><br>**Constraints**: *Maximum Length*: `12` | getRoomBedType(): ?string | setRoomBedType(?string roomBedType): void |
| `roomTaxType` | `?string` | Optional | Type of tax, such as tourist or hotel.<br><br>**Constraints**: *Maximum Length*: `10` | getRoomTaxType(): ?string | setRoomTaxType(?string roomTaxType): void |
| `roomRateType` | `?string` | Optional | Type of rate, such as corporate or senior citizen.<br><br>**Constraints**: *Maximum Length*: `12` | getRoomRateType(): ?string | setRoomRateType(?string roomRateType): void |
| `guestName` | `?string` | Optional | Name of the guest under which the room is reserved.<br><br>**Constraints**: *Maximum Length*: `40` | getGuestName(): ?string | setGuestName(?string guestName): void |
| `customerServicePhoneNumber` | `?string` | Optional | Your toll-free customer service phone number.<br><br>**Constraints**: *Maximum Length*: `17` | getCustomerServicePhoneNumber(): ?string | setCustomerServicePhoneNumber(?string customerServicePhoneNumber): void |
| `corporateClientCode` | `?string` | Optional | Code assigned to a business. You can use this code to identify corporate rates and discounts for guests.<br><br>**Constraints**: *Maximum Length*: `17` | getCorporateClientCode(): ?string | setCorporateClientCode(?string corporateClientCode): void |
| `additionalDiscountAmount` | `?string` | Optional | Amount of an additional coupon or discount.<br><br>**Constraints**: *Maximum Length*: `12` | getAdditionalDiscountAmount(): ?string | setAdditionalDiscountAmount(?string additionalDiscountAmount): void |
| `roomLocation` | `?string` | Optional | Location of room, such as lake view or ocean view.<br><br>**Constraints**: *Maximum Length*: `10` | getRoomLocation(): ?string | setRoomLocation(?string roomLocation): void |
| `specialProgramCode` | `?string` | Optional | Code that identifies special circumstances.<br>Possible values:<br><br>- `1`: lodging (default)<br>- `2`: no show reservation<br>- `3`: advanced deposit<br><br>**Constraints**: *Maximum Length*: `1` | getSpecialProgramCode(): ?string | setSpecialProgramCode(?string specialProgramCode): void |
| `totalTaxAmount` | `?string` | Optional | Total tax amount.<br><br>**Constraints**: *Maximum Length*: `12` | getTotalTaxAmount(): ?string | setTotalTaxAmount(?string totalTaxAmount): void |
| `prepaidCost` | `?string` | Optional | Prepaid amount, such as a deposit.<br><br>**Constraints**: *Maximum Length*: `12` | getPrepaidCost(): ?string | setPrepaidCost(?string prepaidCost): void |
| `foodAndBeverageCost` | `?string` | Optional | Cost for all food and beverages.<br><br>**Constraints**: *Maximum Length*: `12` | getFoodAndBeverageCost(): ?string | setFoodAndBeverageCost(?string foodAndBeverageCost): void |
| `roomTaxAmount` | `?string` | Optional | Total tax for the room.<br><br>**Constraints**: *Maximum Length*: `12` | getRoomTaxAmount(): ?string | setRoomTaxAmount(?string roomTaxAmount): void |
| `adjustmentAmount` | `?string` | Optional | Adjusted amount charged in addition to the reservation amount after the stay is complete.<br><br>**Constraints**: *Maximum Length*: `12` | getAdjustmentAmount(): ?string | setAdjustmentAmount(?string adjustmentAmount): void |
| `phoneCost` | `?string` | Optional | Cost of telephone services.<br><br>**Constraints**: *Maximum Length*: `12` | getPhoneCost(): ?string | setPhoneCost(?string phoneCost): void |
| `restaurantCost` | `?string` | Optional | Cost of restaurant purchases<br><br>**Constraints**: *Maximum Length*: `12` | getRestaurantCost(): ?string | setRestaurantCost(?string restaurantCost): void |
| `roomServiceCost` | `?string` | Optional | Cost of room service.<br><br>**Constraints**: *Maximum Length*: `12` | getRoomServiceCost(): ?string | setRoomServiceCost(?string roomServiceCost): void |
| `miniBarCost` | `?string` | Optional | Cost of mini-bar purchases.<br><br>**Constraints**: *Maximum Length*: `12` | getMiniBarCost(): ?string | setMiniBarCost(?string miniBarCost): void |
| `laundryCost` | `?string` | Optional | Cost of laundry services.<br><br>**Constraints**: *Maximum Length*: `12` | getLaundryCost(): ?string | setLaundryCost(?string laundryCost): void |
| `miscellaneousCost` | `?string` | Optional | Miscellaneous costs.<br><br>**Constraints**: *Maximum Length*: `12` | getMiscellaneousCost(): ?string | setMiscellaneousCost(?string miscellaneousCost): void |
| `giftShopCost` | `?string` | Optional | Cost of gift shop purchases.<br><br>**Constraints**: *Maximum Length*: `12` | getGiftShopCost(): ?string | setGiftShopCost(?string giftShopCost): void |
| `movieCost` | `?string` | Optional | Cost of movies.<br><br>**Constraints**: *Maximum Length*: `12` | getMovieCost(): ?string | setMovieCost(?string movieCost): void |
| `healthClubCost` | `?string` | Optional | Cost of health club services.<br><br>**Constraints**: *Maximum Length*: `12` | getHealthClubCost(): ?string | setHealthClubCost(?string healthClubCost): void |
| `valetParkingCost` | `?string` | Optional | Cost of valet parking services.<br><br>**Constraints**: *Maximum Length*: `12` | getValetParkingCost(): ?string | setValetParkingCost(?string valetParkingCost): void |
| `cashDisbursementCost` | `?string` | Optional | Cost of the cash that was disbursed plus any associated service fees<br><br>**Constraints**: *Maximum Length*: `12` | getCashDisbursementCost(): ?string | setCashDisbursementCost(?string cashDisbursementCost): void |
| `nonRoomCost` | `?string` | Optional | Cost of non-room purchases, such as meals and gifts.<br><br>**Constraints**: *Maximum Length*: `12` | getNonRoomCost(): ?string | setNonRoomCost(?string nonRoomCost): void |
| `businessCenterCost` | `?string` | Optional | Cost of business center services.<br><br>**Constraints**: *Maximum Length*: `12` | getBusinessCenterCost(): ?string | setBusinessCenterCost(?string businessCenterCost): void |
| `loungeBarCost` | `?string` | Optional | Cost of lounge and bar purchases.<br><br>**Constraints**: *Maximum Length*: `12` | getLoungeBarCost(): ?string | setLoungeBarCost(?string loungeBarCost): void |
| `transportationCost` | `?string` | Optional | Cost of transportation services.<br><br>**Constraints**: *Maximum Length*: `12` | getTransportationCost(): ?string | setTransportationCost(?string transportationCost): void |
| `gratuityAmount` | `?string` | Optional | Gratuity.<br><br>**Constraints**: *Maximum Length*: `12` | getGratuityAmount(): ?string | setGratuityAmount(?string gratuityAmount): void |
| `conferenceRoomCost` | `?string` | Optional | Cost of conference room services.<br><br>**Constraints**: *Maximum Length*: `12` | getConferenceRoomCost(): ?string | setConferenceRoomCost(?string conferenceRoomCost): void |
| `audioVisualCost` | `?string` | Optional | Cost of audio visual services.<br><br>**Constraints**: *Maximum Length*: `12` | getAudioVisualCost(): ?string | setAudioVisualCost(?string audioVisualCost): void |
| `banquestCost` | `?string` | Optional | Cost of banquet services.<br><br>**Constraints**: *Maximum Length*: `12` | getBanquestCost(): ?string | setBanquestCost(?string banquestCost): void |
| `nonRoomTaxAmount` | `?string` | Optional | Tax on non-room purchases.<br><br>**Constraints**: *Maximum Length*: `12` | getNonRoomTaxAmount(): ?string | setNonRoomTaxAmount(?string nonRoomTaxAmount): void |
| `earlyCheckOutCost` | `?string` | Optional | Service fee for early departure.<br><br>**Constraints**: *Maximum Length*: `12` | getEarlyCheckOutCost(): ?string | setEarlyCheckOutCost(?string earlyCheckOutCost): void |
| `internetAccessCost` | `?string` | Optional | Cost of Internet access.<br><br>**Constraints**: *Maximum Length*: `12` | getInternetAccessCost(): ?string | setInternetAccessCost(?string internetAccessCost): void |
| `name` | `?string` | Optional | Name of the hotel for which the reservation is for. Mandatory in case the<br>merchant’s business type is Hotel.<br><br>**Constraints**: *Maximum Length*: `255` | getName(): ?string | setName(?string name): void |
| `hotelName` | `?string` | Optional | The name of the hotel for which the reservation was made. | getHotelName(): ?string | setHotelName(?string hotelName): void |
| `checkInDateTime` | `?string` | Optional | The date of the check-in in GMT+8 offset. | getCheckInDateTime(): ?string | setCheckInDateTime(?string checkInDateTime): void |
| `checkOutDateTime` | `?string` | Optional | The date of the check-out in GMT+8 offset. | getCheckOutDateTime(): ?string | setCheckOutDateTime(?string checkOutDateTime): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LodgingBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RoomBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$lodging = LodgingBuilder::init()
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
    ->build();
```

