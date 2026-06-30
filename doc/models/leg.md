
# Leg

*This model accepts additional fields of type array.*

## Structure

`Leg`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `carrierCode` | `?string` | Optional | IATA code for the carrier for this leg of the trip.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `4` | getCarrierCode(): ?string | setCarrierCode(?string carrierCode): void |
| `flightNumber` | `?string` | Optional | Flight number for this leg of the trip.<br>Restrictions are limitations for the ticket based on the type of fare, such as a nonrefundable ticket or a 3-day minimum stay.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `6` | getFlightNumber(): ?string | setFlightNumber(?string flightNumber): void |
| `originatingAirportCode` | `?string` | Optional | IATA code for the originating airport for this leg of the trip.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `5` | getOriginatingAirportCode(): ?string | setOriginatingAirportCode(?string originatingAirportCode): void |
| `class` | `?string` | Optional | IATA code for the class of service for this leg of the trip.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `3` | getClass(): ?string | setClass(?string class): void |
| `stopoverIndicator` | `?int` | Optional | Code that indicates whether a stopover is allowed on this leg of the trip. Possible values:<br><br>- `O` (capital letter “O”) (default): Stopover allowed<br>- `X` (capital letter “X”): Stopover not allowed<br>  Format: English characters only.<br>  Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>  Optional request field for travel legs. | getStopoverIndicator(): ?int | setStopoverIndicator(?int stopoverIndicator): void |
| `departureDate` | `?int` | Optional | Departure date for the first leg of the trip.<br>Format: `YYYYMMDD`.<br>Format: English characters only.<br>Optional request field for travel legs. | getDepartureDate(): ?int | setDepartureDate(?int departureDate): void |
| `destinationAirportCode` | `?string` | Optional | IATA code for the destination airport for this leg of the trip.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `3` | getDestinationAirportCode(): ?string | setDestinationAirportCode(?string destinationAirportCode): void |
| `fareBasis` | `?string` | Optional | Code for the fare basis for this leg of the trip.<br>The fare basis is assigned by the carriers and indicates a particular ticket type,<br>such as business class or discounted/nonrefundable.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Format: English characters only.<br>Optional request field for travel legs.auto_rental_regular_mileage_cost<br><br>**Constraints**: *Maximum Length*: `15` | getFareBasis(): ?string | setFareBasis(?string fareBasis): void |
| `departTaxAmount` | `?string` | Optional | Amount of departure tax for this leg of the trip.<br><br>**Constraints**: *Maximum Length*: `12` | getDepartTaxAmount(): ?string | setDepartTaxAmount(?string departTaxAmount): void |
| `conjunctionTicket` | `?string` | Optional | Ticket that contains additional coupons for this leg of the trip on an itinerary that has more than four segments.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `25` | getConjunctionTicket(): ?string | setConjunctionTicket(?string conjunctionTicket): void |
| `exchangeTicketNumber` | `?string` | Optional | New ticket number that is issued when the ticket is exchanged for this leg of the trip.<br>Restrictions are limitations for the ticket based on the type of fare, such as a nonrefundable ticket or a 3-day minimum stay.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `25` | getExchangeTicketNumber(): ?string | setExchangeTicketNumber(?string exchangeTicketNumber): void |
| `couponNumber` | `?string` | Optional | Coupon number. Each leg on the ticket requires a separate coupon, and each coupon is identified by the coupon number.<br>Format: English characters only.<br>Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `1` | getCouponNumber(): ?string | setCouponNumber(?string couponNumber): void |
| `departureTime` | `?int` | Optional | Time of departure for this leg of the trip. The format is military time and HHMM:<br>If not all zeros, then the hours must be `00-23` and the minutes must be `00-59`.<br>Format: English characters only.<br>Optional request field for travel legs. | getDepartureTime(): ?int | setDepartureTime(?int departureTime): void |
| `departureTimeMeridian` | `?string` | Optional | AM or PM for the departure time.<br>Possible values:<br><br>- A: 12:00 midnight to 11:59 a.m.<br>- P: 12:00 noon to 11:59 p.m<br>  Format: English characters only.<br>  Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>  Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `1` | getDepartureTimeMeridian(): ?string | setDepartureTimeMeridian(?string departureTimeMeridian): void |
| `arrivalTime` | `?int` | Optional | Time of arrival for this leg of the trip.<br>The format is military time and HHMM:<br>If not all zeros, then the hours must be `00-23` and the minutes must be `00-59`<br>Format: English characters only.<br>Optional request field for travel legs. | getArrivalTime(): ?int | setArrivalTime(?int arrivalTime): void |
| `arrivalTimeMeridian` | `?string` | Optional | AM or PM for the arrival time for this leg of the trip.<br>Possible values:<br><br>- `A`: 12:00 midnight to 11:59 a.m.<br>- `P`: 12:00 noon to 11:59 p.m.<br>  Format: English characters only.<br>  Restricted string data type that indicates a sequence of letters, numbers, and spaces; special characters are not included.<br>  Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `1` | getArrivalTimeMeridian(): ?string | setArrivalTimeMeridian(?string arrivalTimeMeridian): void |
| `endorsementsRestrictions` | `?string` | Optional | Notes or notations about endorsements and restrictions for this leg of the trip.<br>Endorsements can be notations added by the travel agency, including mandatory government-required notations such as value added tax.<br>Restrictions are limitations for the ticket based on the type of fare, such as a nonrefundable ticket or a 3-day minimum stay.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `20` | getEndorsementsRestrictions(): ?string | setEndorsementsRestrictions(?string endorsementsRestrictions): void |
| `totalFareAmount` | `?string` | Optional | Total fare for this leg of the trip.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `15` | getTotalFareAmount(): ?string | setTotalFareAmount(?string totalFareAmount): void |
| `feeAmount` | `?string` | Optional | Fee for this leg of the trip, such as an airport fee or country fee.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `12` | getFeeAmount(): ?string | setFeeAmount(?string feeAmount): void |
| `taxAmount` | `?string` | Optional | Tax for this leg of the trip.<br>Format: English characters only.<br>Optional request field for travel legs.<br><br>**Constraints**: *Maximum Length*: `12` | getTaxAmount(): ?string | setTaxAmount(?string taxAmount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\LegBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$leg = LegBuilder::init()
    ->carrierCode('carrierCode0')
    ->flightNumber('flightNumber4')
    ->originatingAirportCode('originatingAirportCode4')
    ->class('class0')
    ->stopoverIndicator(34)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

