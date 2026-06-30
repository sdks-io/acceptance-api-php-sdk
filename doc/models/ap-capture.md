
# Ap Capture

*This model accepts additional fields of type array.*

## Structure

`ApCapture`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | The reason why the captured payment status is PENDING or DENIED.<br>BUYER_COMPLAINT	The payer initiated a dispute for this captured payment with processor.<br>CHARGEBACK	The captured funds were reversed in response to the payer disputing this captured payment with the issuer of the financial instrument used to pay for this captured payment.<br>ECHECK	The payer paid by an eCheck that has not yet cleared.<br>INTERNATIONAL_WITHDRAWAL	Visit your online account. In your Account Overview, accept and deny this payment.<br>OTHER	No additional specific reason can be provided. For more information about this captured payment, visit your account online or contact processor.<br>PENDING_REVIEW	The captured payment is pending manual review.<br>RECEIVING_PREFERENCE_MANDATES_MANUAL_ACTION	The payee has not yet set up appropriate receiving preferences for their account. For more information about how to accept or deny this payment, visit your account online. This reason is typically offered in scenarios such as when the currency of the captured payment is different from the primary holding currency of the payee.<br>REFUNDED	The captured funds were refunded.<br>TRANSACTION_APPROVED_AWAITING_FUNDING	The payer must send the funds for this captured payment. This code generally appears for manual EFTs.<br>UNILATERAL	The payee does not have a processor account.<br>VERIFICATION_REQUIRED	The payee's processor account is not verified.<br>String with values,<br>`BUYER_COMPLAINT`<br>`CHARGEBACK`<br>`ECHECK`<br>`INTERNATIONAL_WITHDRAWAL`<br>`OTHER`<br>`PENDING_REVIEW`<br>`RECEIVING_PREFERENCE_MANDATES_MANUAL_ACTION`<br>`REFUNDED`<br>`TRANSACTION_APPROVED_AWAITING_FUNDING`<br>`UNILATERAL`<br>`VERIFICATION_REQUIRED` | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ApCaptureBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$apCapture = ApCaptureBuilder::init()
    ->reason('reason8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

