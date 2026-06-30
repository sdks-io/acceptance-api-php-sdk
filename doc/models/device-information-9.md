
# Device Information 9

*This model accepts additional fields of type array.*

## Structure

`DeviceInformation9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ipAddress` | `?string` | Optional | IP address of the customer.<br><br>#### Used by<br><br>**Authorization, Capture, and Credit**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `45` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `hostName` | `?string` | Optional | DNS resolved hostname from `ipAddress`.<br><br>**Constraints**: *Maximum Length*: `60` | getHostName(): ?string | setHostName(?string hostName): void |
| `cookiesAccepted` | `?string` | Optional | Whether the customer’s browser accepts cookies. This field can contain one of the following values:<br><br>- `yes`: The customer’s browser accepts cookies.<br>- `no`: The customer’s browser does not accept cookies. | getCookiesAccepted(): ?string | setCookiesAccepted(?string cookiesAccepted): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$deviceInformation9 = DeviceInformation9Builder::init()
    ->ipAddress('ipAddress2')
    ->hostName('hostName2')
    ->cookiesAccepted('cookiesAccepted0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

