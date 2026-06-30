
# Return Address

*This model accepts additional fields of type array.*

## Structure

`ReturnAddress`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | City where the auto was returned to the rental agency.<br><br>**Constraints**: *Maximum Length*: `25` | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | State in which the auto was returned to the rental agency. Use the [State, Province, and Territory Codes for the United States and Canada](<br><br>For authorizations, this field is supported for Visa, MasterCard, and American Express.<br><br>For captures, this field is supported only for MasterCard and American Express.<br><br>**Constraints**: *Maximum Length*: `3` | getState(): ?string | setState(?string state): void |
| `country` | `?string` | Optional | Country where the auto was returned to the rental agency. Use the [ISO Standard Country Codes](<br><br>**Constraints**: *Maximum Length*: `3` | getCountry(): ?string | setCountry(?string country): void |
| `locationId` | `?string` | Optional | Code, address, phone number, etc. used to identify the location of the auto rental return.<br>This field is supported only for MasterCard and American Express.<br><br>**Constraints**: *Maximum Length*: `10` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `address1` | `?string` | Optional | When merchant wants to send the rental address's street address.<br><br>**Constraints**: *Maximum Length*: `50` | getAddress1(): ?string | setAddress1(?string address1): void |
| `postalCode` | `?string` | Optional | When merchant wants to send the return address's postal code.<br><br>**Constraints**: *Maximum Length*: `50` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `location` | `?string` | Optional | This field contains the location where the taxi passenger was dropped off or where the auto rental vehicle was returned.<br><br>**Constraints**: *Maximum Length*: `38` | getLocation(): ?string | setLocation(?string location): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ReturnAddressBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$returnAddress = ReturnAddressBuilder::init()
    ->city('city0')
    ->state('state4')
    ->country('country4')
    ->locationId('locationId2')
    ->address1('address12')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

