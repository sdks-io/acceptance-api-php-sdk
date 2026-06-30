
# Passenger

Contains travel-related passenger details used by DM service only.

*This model accepts additional fields of type array.*

## Structure

`Passenger`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Passenger classification associated with the price of the ticket. You can use one of the following values:<br><br>- `ADT`: Adult<br>- `CNN`: Child<br>- `INF`: Infant<br>- `YTH`: Youth<br>- `STU`: Student<br>- `SCR`: Senior Citizen<br>- `MIL`: Military<br><br>**Constraints**: *Maximum Length*: `32` | getType(): ?string | setType(?string type): void |
| `status` | `?string` | Optional | Your company's passenger classification, such as with a frequent flyer program. In this case, you might use<br>values such as `standard`, `gold`, or `platinum`.<br><br>**Constraints**: *Maximum Length*: `32` | getStatus(): ?string | setStatus(?string status): void |
| `phone` | `?string` | Optional | Passenger's phone number. If the order is from outside the U.S., Visa Acceptance recommends that you include<br>the [ISO Standard Country Codes](<br><br>**Constraints**: *Maximum Length*: `15` | getPhone(): ?string | setPhone(?string phone): void |
| `firstName` | `?string` | Optional | Passenger's first name.<br><br>**Constraints**: *Maximum Length*: `60` | getFirstName(): ?string | setFirstName(?string firstName): void |
| `lastName` | `?string` | Optional | Passenger's last name.<br><br>**Constraints**: *Maximum Length*: `60` | getLastName(): ?string | setLastName(?string lastName): void |
| `id` | `?string` | Optional | ID of the passenger to whom the ticket was issued. For example, you can use this field for the frequent flyer<br>number.<br><br>**Constraints**: *Maximum Length*: `40` | getId(): ?string | setId(?string id): void |
| `email` | `?string` | Optional | Passenger's email address, including the full domain name, such as jdoe@example.com.<br><br>**Constraints**: *Maximum Length*: `255` | getEmail(): ?string | setEmail(?string email): void |
| `nationality` | `?string` | Optional | Passenger's nationality country. Use the two character [ISO Standard Country Codes](<br><br>**Constraints**: *Maximum Length*: `2` | getNationality(): ?string | setNationality(?string nationality): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PassengerBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$passenger = PassengerBuilder::init()
    ->type('type0')
    ->status('status2')
    ->phone('phone0')
    ->firstName('firstName6')
    ->lastName('lastName4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

