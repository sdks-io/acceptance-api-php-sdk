
# First Destination

*This model accepts additional fields of type array.*

## Structure

`FirstDestination`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | Country of first destination on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getCountry(): ?string | setCountry(?string country): void |
| `locality` | `?string` | Optional | City of first destination on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getLocality(): ?string | setLocality(?string locality): void |
| `latitude` | `?string` | Optional | Latitude of first destination on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLatitude(): ?string | setLatitude(?string latitude): void |
| `longitude` | `?string` | Optional | Longitude of first destination on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLongitude(): ?string | setLongitude(?string longitude): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\FirstDestinationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$firstDestination = FirstDestinationBuilder::init()
    ->country('country6')
    ->locality('locality2')
    ->latitude('latitude4')
    ->longitude('longitude6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

