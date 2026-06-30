
# Info Codes

*This model accepts additional fields of type array.*

## Structure

`InfoCodes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `velocity` | `?(string[])` | Optional | List of information codes triggered by the order. These information codes were generated when you created<br>the order and product velocity rules and are returned so that you can associate them with the rules. | getVelocity(): ?array | setVelocity(?array velocity): void |
| `address` | `?(string[])` | Optional | Indicates a mismatch between the customer’s billing and shipping addresses. | getAddress(): ?array | setAddress(?array address): void |
| `customerList` | `?(string[])` | Optional | Indicates that customer information is associated with transactions that are either on the negative or<br>the positive list. | getCustomerList(): ?array | setCustomerList(?array customerList): void |
| `deviceBehavior` | `?(string[])` | Optional | Indicates the device behavior information code(s) returned from device fingerprinting. | getDeviceBehavior(): ?array | setDeviceBehavior(?array deviceBehavior): void |
| `identityChange` | `?(string[])` | Optional | Indicates excessive identity changes. The threshold is variable depending on the identity elements being<br>compared. | getIdentityChange(): ?array | setIdentityChange(?array identityChange): void |
| `internet` | `?(string[])` | Optional | Indicates a problem with the customer’s email address, IP address, or billing address. | getInternet(): ?array | setInternet(?array internet): void |
| `phone` | `?(string[])` | Optional | Indicates a problem with the customer’s phone number. | getPhone(): ?array | setPhone(?array phone): void |
| `suspicious` | `?(string[])` | Optional | Indicates that the customer provided potentially suspicious information. | getSuspicious(): ?array | setSuspicious(?array suspicious): void |
| `globalVelocity` | `?(string[])` | Optional | Indicates that the customer has a high purchase frequency. | getGlobalVelocity(): ?array | setGlobalVelocity(?array globalVelocity): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\InfoCodesBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$infoCodes = InfoCodesBuilder::init()
    ->velocity(
        [
            'velocity8',
            'velocity9',
            'velocity0'
        ]
    )
    ->address(
        [
            'address8',
            'address9',
            'address0'
        ]
    )
    ->customerList(
        [
            'customerList1'
        ]
    )
    ->deviceBehavior(
        [
            'deviceBehavior1'
        ]
    )
    ->identityChange(
        [
            'identityChange2',
            'identityChange3'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

