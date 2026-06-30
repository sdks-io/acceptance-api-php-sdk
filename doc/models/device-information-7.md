
# Device Information 7

*This model accepts additional fields of type array.*

## Structure

`DeviceInformation7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ipAddress` | `?string` | Optional | IP address of the customer.<br><br>#### Used by<br><br>**Authorization, Capture, and Credit**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `45` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `deviceType` | `?string` | Optional | The device type at the client side.<br><br>**Constraints**: *Maximum Length*: `60` | getDeviceType(): ?string | setDeviceType(?string deviceType): void |
| `id` | `?string` | Optional | ../../../commons/definitions/device.yaml#/properties/id<br><br>**Constraints**: *Maximum Length*: `50` | getId(): ?string | setId(?string id): void |
| `userAgent` | `?string` | Optional | Customer’s browser as identified from the HTTP header data. For example, `Mozilla` is the value that identifies<br>the Netscape browser.<br><br>**Constraints**: *Maximum Length*: `40` | getUserAgent(): ?string | setUserAgent(?string userAgent): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation7Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$deviceInformation7 = DeviceInformation7Builder::init()
    ->ipAddress('ipAddress4')
    ->deviceType('deviceType8')
    ->id('id4')
    ->userAgent('userAgent0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

