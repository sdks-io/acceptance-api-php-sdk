
# Partner 1

*This model accepts additional fields of type array.*

## Structure

`Partner1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `originalTransactionId` | `?string` | Optional | Value that links the previous transaction to the current follow-on request. This value is assigned by the client<br>software that is installed on the POS terminal, which makes it available to the terminal’s software and to<br>Visa Acceptance. Therefore, you can use this value to reconcile transactions between Visa Acceptance and the terminal’s<br>software.<br><br>Visa Acceptance does not forward this value to the processor. Instead, the value is forwarded to the Visa Acceptance<br>reporting functionality.<br><br>This field is supported only on these processors:<br><br>- American Express Direct<br>- Credit Mutuel-CIC<br>- FDC Nashville Global<br>- OmniPay Direct<br>- SIX<br><br>Optional field.<br><br>**Constraints**: *Maximum Length*: `32` | getOriginalTransactionId(): ?string | setOriginalTransactionId(?string originalTransactionId): void |
| `developerId` | `?string` | Optional | Identifier for the developer that helped integrate a partner solution to Visa Acceptance.<br><br>Send this value in all requests that are sent through the partner solutions built by that developer.<br>Visa Acceptance assigns the ID to the developer.<br><br>**Note** When you see a developer ID of 999 in reports, the developer ID that was submitted is incorrect.<br><br>**Constraints**: *Maximum Length*: `8` | getDeveloperId(): ?string | setDeveloperId(?string developerId): void |
| `solutionId` | `?string` | Optional | Identifier for the partner that is integrated to Visa Acceptance.<br><br>Send this value in all requests that are sent through the partner solution. Visa Acceptance assigns the ID to the partner.<br><br>**Note** When you see a solutionId of 999 in reports, the solutionId that was submitted is incorrect.<br><br>**Constraints**: *Maximum Length*: `8` | getSolutionId(): ?string | setSolutionId(?string solutionId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Partner1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$partner1 = Partner1Builder::init()
    ->originalTransactionId('originalTransactionId2')
    ->developerId('developerId2')
    ->solutionId('solutionId4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

