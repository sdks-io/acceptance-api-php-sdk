
# Capture Options

*This model accepts additional fields of type array.*

## Structure

`CaptureOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `captureSequenceNumber` | `?int` | Optional | Capture number when requesting multiple partial captures for one authorization.<br>Used along with `totalCaptureCount` to track which capture is being processed.<br><br>For example, the second of five captures would be passed to Visa Acceptance as:<br><br>- `captureSequenceNumber_ = 2`, and<br>- `totalCaptureCount = 5`<br><br>**Constraints**: `>= 1`, `<= 99` | getCaptureSequenceNumber(): ?int | setCaptureSequenceNumber(?int captureSequenceNumber): void |
| `totalCaptureCount` | `?int` | Optional | Total number of captures when requesting multiple partial captures for one payment.<br>Used along with `captureSequenceNumber` field to track which capture is being processed.<br><br>For example, the second of five captures would be passed to Visa Acceptance as:<br><br>- `captureSequenceNumber = 2`, and<br>- `totalCaptureCount = 5`<br><br>**Constraints**: `>= 1`, `<= 99` | getTotalCaptureCount(): ?int | setTotalCaptureCount(?int totalCaptureCount): void |
| `dateToCapture` | `?string` | Optional | Date on which you want the capture to occur. This field is supported only for Visa Acceptance through VisaNet.<br>Format: `MMDD`<br><br>#### Used by<br><br>**Authorization**<br>Optional field.<br><br>**Constraints**: *Maximum Length*: `4` | getDateToCapture(): ?string | setDateToCapture(?string dateToCapture): void |
| `isFinal` | `?string` | Optional | Indicates whether to release the authorization hold on the remaining funds.  <br>Possible Values:<br><br>- `true`<br>- `false`<br><br>**Constraints**: *Maximum Length*: `5` | getIsFinal(): ?string | setIsFinal(?string isFinal): void |
| `notes` | `?string` | Optional | An informational note about this settlement. Appears in both the payer's transaction history and the emails that the payer receives.<br><br>**Constraints**: *Maximum Length*: `255` | getNotes(): ?string | setNotes(?string notes): void |
| `reconciliationId` | `?string` | Optional | Used for authbill request when capture field equals true<br><br>**Constraints**: *Maximum Length*: `60` | getReconciliationId(): ?string | setReconciliationId(?string reconciliationId): void |
| `reconciliationIdAlternate` | `?string` | Optional | Used by Nike merchant to send 12 digit order number<br><br>**Constraints**: *Maximum Length*: `12` | getReconciliationIdAlternate(): ?string | setReconciliationIdAlternate(?string reconciliationIdAlternate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CaptureOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$captureOptions = CaptureOptionsBuilder::init()
    ->captureSequenceNumber(99)
    ->totalCaptureCount(60)
    ->dateToCapture('dateToCapture0')
    ->isFinal('isFinal2')
    ->notes('notes2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

