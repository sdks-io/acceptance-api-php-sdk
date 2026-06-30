
# Actual Final Destination

*This model accepts additional fields of type array.*

## Structure

`ActualFinalDestination`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `country` | `?string` | Optional | Country of actual final destination on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getCountry(): ?string | setCountry(?string country): void |
| `locality` | `?string` | Optional | City of actual final destination on the route.<br><br>**Constraints**: *Maximum Length*: `90` | getLocality(): ?string | setLocality(?string locality): void |
| `latitude` | `?string` | Optional | Latitude of actual final destination on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLatitude(): ?string | setLatitude(?string latitude): void |
| `longitude` | `?string` | Optional | Longitude of actual final destination on the route.<br><br>**Constraints**: *Maximum Length*: `10` | getLongitude(): ?string | setLongitude(?string longitude): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ActualFinalDestinationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$actualFinalDestination = ActualFinalDestinationBuilder::init()
    ->country('country6')
    ->locality('locality2')
    ->latitude('latitude4')
    ->longitude('longitude6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

