
# Authorization Options 2

*This model accepts additional fields of type array.*

## Structure

`AuthorizationOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `serviceType` | `?string` | Optional | Field is used for back-to-back funding transaction and can be defined as a payment flow that automatically transfers funds through a real-time<br>funding or a live-load. This type of transaction can also be connected to a purchase.<br>In back-to-back funding of general purpose card that is used to make a purchase, two separate accounts are involved:<br><br>- account one is used to make the purchase<br>- account two is used to automatically fund or reimburse account one<br><br>Possible values:<br><br>- 0B = back to back funding transaction<br>- 00 = normal transaction<br>- 01 = originator hold<br>- 02 = Visa deferred OCT hold, default interval<br>- 03 = Visa deferred OCT hold, user-defined interval<br>- 09 = Cancel pending deferred OCT request<br>- 0I = Visa Direct custom program 1<br>- 0Q = uery the status of the deferred OCT<br>- A0 = Alias Directory 2<br><br>**Constraints**: *Maximum Length*: `10` | getServiceType(): ?string | setServiceType(?string serviceType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationOptions2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationOptions2 = AuthorizationOptions2Builder::init()
    ->serviceType('serviceType2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

