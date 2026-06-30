
# Device Information 1

*This model accepts additional fields of type array.*

## Structure

`DeviceInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `hostName` | `?string` | Optional | DNS resolved hostname from `ipAddress`.<br><br>**Constraints**: *Maximum Length*: `60` | getHostName(): ?string | setHostName(?string hostName): void |
| `ipAddress` | `?string` | Optional | IP address of the customer.<br><br>#### Used by<br><br>**Authorization, Capture, and Credit**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `45` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `userAgent` | `?string` | Optional | Customer’s browser as identified from the HTTP header data. For example, `Mozilla` is the value that identifies<br>the Netscape browser.<br><br>**Constraints**: *Maximum Length*: `40` | getUserAgent(): ?string | setUserAgent(?string userAgent): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$deviceInformation1 = DeviceInformation1Builder::init()
    ->hostName('hostName8')
    ->ipAddress('ipAddress6')
    ->userAgent('userAgent2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

