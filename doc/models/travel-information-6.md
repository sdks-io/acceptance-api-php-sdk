
# Travel Information 6

*This model accepts additional fields of type array.*

## Structure

`TravelInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `autoRental` | [`?AutoRental5`](../../doc/models/auto-rental-5.md) | Optional | - | getAutoRental(): ?AutoRental5 | setAutoRental(?AutoRental5 autoRental): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TravelInformation6Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AutoRental5Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\RentalAddressBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\ReturnAddressBuilder;

$travelInformation6 = TravelInformation6Builder::init()
    ->autoRental(
        AutoRental5Builder::init()
            ->companyName('companyName2')
            ->affiliateName('affiliateName4')
            ->rentalAddress(
                RentalAddressBuilder::init()
                    ->city('city6')
                    ->state('state0')
                    ->country('country8')
                    ->locationId('locationId6')
                    ->address1('address12')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->returnAddress(
                ReturnAddressBuilder::init()
                    ->city('city0')
                    ->state('state4')
                    ->country('country4')
                    ->locationId('locationId2')
                    ->address1('address12')
                    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                    ->build()
            )
            ->returnDateTime('returnDateTime2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

