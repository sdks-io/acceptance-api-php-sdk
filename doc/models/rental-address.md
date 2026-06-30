
# Rental Address

*This model accepts additional fields of type array.*

## Structure

`RentalAddress`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `city` | `?string` | Optional | City in which the auto was rented.<br><br>For authorizations, this field is supported for Visa, MasterCard, and American Express.<br><br>For captures, this field is supported only for American Express.<br><br>For all other card types, this field is ignored.<br><br>**Constraints**: *Maximum Length*: `25` | getCity(): ?string | setCity(?string city): void |
| `state` | `?string` | Optional | State in which the auto was rented. Use the [State, Province, and Territory Codes for the United States and Canada](<br><br>**Constraints**: *Maximum Length*: `3` | getState(): ?string | setState(?string state): void |
| `country` | `?string` | Optional | Country where the auto was rented. Use the [ISO Standard Country Codes.](<br>This field is supported only for American Express.<br><br>**Constraints**: *Maximum Length*: `3` | getCountry(): ?string | setCountry(?string country): void |
| `locationId` | `?string` | Optional | The agency code, address, phone number, etc., used to identify the location where the vehicle was rented.<br><br>**Constraints**: *Maximum Length*: `10` | getLocationId(): ?string | setLocationId(?string locationId): void |
| `address1` | `?string` | Optional | Address from where the vehicle was rented.<br><br>**Constraints**: *Maximum Length*: `13` | getAddress1(): ?string | setAddress1(?string address1): void |
| `address2` | `?string` | Optional | Address from where the vehicle was rented.<br><br>**Constraints**: *Maximum Length*: `13` | getAddress2(): ?string | setAddress2(?string address2): void |
| `postalCode` | `?string` | Optional | When merchant wants to send the rental address's postal code.<br><br>**Constraints**: *Maximum Length*: `50` | getPostalCode(): ?string | setPostalCode(?string postalCode): void |
| `location` | `?string` | Optional | This field contains the location where a taxi passenger was picked up or where an auto rental vehicle was picked up. In most cases, this is the rental agency's business name that appears on the storefront and/or customer receipts, commonly referred to as the DBA (Doing Business As) name. However, if the vehicle was picked up at another location (e.g., a hotel,auto dealership, repair shop, etc.), the name of that location should be used. This entry must be easily recognized by the Cardmember to avoid unnecessary inquiries. If the name is more than 38  characters, use proper and meaningful abbreviation, when possible.<br><br>**Constraints**: *Maximum Length*: `38` | getLocation(): ?string | setLocation(?string location): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RentalAddressBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$rentalAddress = RentalAddressBuilder::init()
    ->city('city6')
    ->state('state0')
    ->country('country8')
    ->locationId('locationId6')
    ->address1('address12')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

