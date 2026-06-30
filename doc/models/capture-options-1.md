
# Capture Options 1

*This model accepts additional fields of type array.*

## Structure

`CaptureOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `finalCapture` | `?string` | Optional | Indicates whether you can make additional captures against the authorized payment.<br>Set to true if you do not intend to capture additional payments against the authorization.<br>Set to false if you intend to capture additional payments<br>Possible Values:<br><br>- `true`<br>- `false`<br><br>**Constraints**: *Maximum Length*: `5` | getFinalCapture(): ?string | setFinalCapture(?string finalCapture): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$captureOptions1 = CaptureOptions1Builder::init()
    ->finalCapture('finalCapture2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

