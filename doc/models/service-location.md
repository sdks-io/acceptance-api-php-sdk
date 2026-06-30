
# Service Location

*This model accepts additional fields of type array.*

## Structure

`ServiceLocation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locality` | `?string` | Optional | #### Visa Platform Connect<br><br>Merchant’s service location city name. When merchant provides services from a location other than the location identified as merchant location.<br><br>**Constraints**: *Maximum Length*: `20` | getLocality(): ?string | setLocality(?string locality): void |
| `countrySubdivisionCode` | `?string` | Optional | #### Visa Platform Connect<br><br>Merchant’s service location country subdivision code. When merchant provides services from a location other than the location identified as merchant location.<br><br>**Constraints**: *Maximum Length*: `9` | getCountrySubdivisionCode(): ?string | setCountrySubdivisionCode(?string countrySubdivisionCode): void |
| `countryCode` | `?string` | Optional | #### Visa Platform Connect<br><br>Merchant’s service location country code. When merchant provides services from a location other than the location identified as merchant location.<br><br>**Constraints**: *Maximum Length*: `3` | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `postalCode` | `?string` | Optional | #### Visa Platform Connect<br><br>Merchant’s service location postal code. When merchant provides services from a location other than the location identified as merchant location.<br><br>**Constraints**: *Maximum Length*: `10` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ServiceLocationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$serviceLocation = ServiceLocationBuilder::init()
    ->locality('locality2')
    ->countrySubdivisionCode('countrySubdivisionCode6')
    ->countryCode('countryCode6')
    ->postalCode('postalCode0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

