
# Transit

*This model accepts additional fields of type array.*

## Structure

`Transit`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `airline` | [`?Airline`](../../doc/models/airline.md) | Optional | - | getAirline(): ?Airline | setAirline(?Airline airline): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TransitBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AirlineBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\TicketIssuerBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$transit = TransitBuilder::init()
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
    ->build();
```

