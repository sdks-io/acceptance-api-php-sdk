
# First Departure

*This model accepts additional fields of type array.*

## Structure

`FirstDeparture`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | Country of first departure on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getCountry(): ?string | setCountry(?string country): void |
| `locality` | `?string` | Optional | City of first departure on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getLocality(): ?string | setLocality(?string locality): void |
| `latitude` | `?string` | Optional | Latitude of first departure on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLatitude(): ?string | setLatitude(?string latitude): void |
| `longitude` | `?string` | Optional | Longitude of first departure on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLongitude(): ?string | setLongitude(?string longitude): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstDepartureBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$firstDeparture = FirstDepartureBuilder::init()
    ->country('country2')
    ->locality('locality8')
    ->latitude('latitude2')
    ->longitude('longitude2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

