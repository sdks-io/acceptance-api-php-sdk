
# Device Information 5

*This model accepts additional fields of type array.*

## Structure

`DeviceInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `httpAcceptBrowserValue` | `?string` | Optional | Value of the Accept header sent by the customer’s web browser.<br>**Note** If the customer’s browser provides a value, you must include it in your request.<br><br>**Constraints**: *Maximum Length*: `255` | getHttpAcceptBrowserValue(): ?string | setHttpAcceptBrowserValue(?string httpAcceptBrowserValue): void |
| `ipAddress` | `?string` | Optional | IP address of the customer.<br><br>#### Used by<br><br>**Authorization, Capture, and Credit**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `45` | getIpAddress(): ?string | setIpAddress(?string ipAddress): void |
| `userAgentBrowserValue` | `?string` | Optional | Value of the User-Agent header sent by the customer’s web browser.<br>Note If the customer’s browser provides a value, you must include it in your request.<br><br>**Constraints**: *Maximum Length*: `255` | getUserAgentBrowserValue(): ?string | setUserAgentBrowserValue(?string userAgentBrowserValue): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DeviceInformation5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$deviceInformation5 = DeviceInformation5Builder::init()
    ->httpAcceptBrowserValue('httpAcceptBrowserValue0')
    ->ipAddress('ipAddress0')
    ->userAgentBrowserValue('userAgentBrowserValue2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

