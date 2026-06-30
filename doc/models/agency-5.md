
# Agency 5

*This model accepts additional fields of type array.*

## Structure

`Agency5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `startDate` | `?string` | Optional | The start date of the agency's service. | getStartDate(): ?string | setStartDate(?string startDate): void |
| `endDate` | `?string` | Optional | The end date of the agency's service. | getEndDate(): ?string | setEndDate(?string endDate): void |
| `changeOfGuest` | `?string` | Optional | Indicates if there is a change of guest. | getChangeOfGuest(): ?string | setChangeOfGuest(?string changeOfGuest): void |
| `countryCode` | `?string` | Optional | The country code of the agency. | getCountryCode(): ?string | setCountryCode(?string countryCode): void |
| `locality` | `?string` | Optional | The locality of the agency. | getLocality(): ?string | setLocality(?string locality): void |
| `postalCode` | `?string` | Optional | The postal code of the agency. | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Agency5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$agency5 = Agency5Builder::init()
    ->startDate('startDate2')
    ->endDate('endDate4')
    ->changeOfGuest('changeOfGuest2')
    ->countryCode('countryCode2')
    ->locality('locality2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

