
# Capture Options 3

*This model accepts additional fields of type array.*

## Structure

`CaptureOptions3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `totalCaptureCount` | `?int` | Optional | Total number of captures when requesting multiple partial captures for one payment.<br>Used along with `captureSequenceNumber` field to track which capture is being processed.<br><br>For example, the second of five captures would be passed to Visa Acceptance as:<br><br>- `captureSequenceNumber = 2`, and<br>- `totalCaptureCount = 5`<br><br>**Constraints**: `>= 1`, `<= 99` | getTotalCaptureCount(): ?int | setTotalCaptureCount(?int totalCaptureCount): void |
| `captureSequenceNumber` | `?int` | Optional | Capture number when requesting multiple partial captures for one authorization.<br>Used along with `totalCaptureCount` to track which capture is being processed.<br><br>For example, the second of five captures would be passed to Visa Acceptance as:<br><br>- `captureSequenceNumber_ = 2`, and<br>- `totalCaptureCount = 5`<br><br>**Constraints**: `>= 1`, `<= 99` | getCaptureSequenceNumber(): ?int | setCaptureSequenceNumber(?int captureSequenceNumber): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureOptions3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$captureOptions3 = CaptureOptions3Builder::init()
    ->totalCaptureCount(8)
    ->captureSequenceNumber(99)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

