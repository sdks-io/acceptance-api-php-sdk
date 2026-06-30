
# Authorization Information

*This model accepts additional fields of type array.*

## Structure

`AuthorizationInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `approvalCode` | `?string` | Optional | The authorization code returned by the processor.<br><br>**Constraints**: *Maximum Length*: `6` | getApprovalCode(): ?string | setApprovalCode(?string approvalCode): void |
| `reasonCode` | `?string` | Optional | Reply flag for the original transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getReasonCode(): ?string | setReasonCode(?string reasonCode): void |
| `reversalSubmitted` | `?string` | Optional | Flag indicating whether a full authorization reversal was successfully submitted.<br><br>Possible values:<br><br>- Y: The authorization reversal was successfully submitted.<br>- N: The authorization reversal was not successfully submitted. You must send a credit request for a refund.<br><br>This field is supported only for **FDC Nashville Global**.<br><br>**Constraints**: *Maximum Length*: `1` | getReversalSubmitted(): ?string | setReversalSubmitted(?string reversalSubmitted): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AuthorizationInformationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$authorizationInformation = AuthorizationInformationBuilder::init()
    ->approvalCode('approvalCode4')
    ->reasonCode('reasonCode8')
    ->reversalSubmitted('reversalSubmitted8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

