
# Complete Mandate 2

*This model accepts additional fields of type array.*

## Structure

`CompleteMandate2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | This field is used to indicate how a payment should be processed.<br><br>Possible values:<br><br>- AUTH: Use this value when you want to authorize a payment within Unified Checkout without capturing it immediately.  Payment types that initiate an immediate transfer of funds are NOT allowed.  If a capture context request includes a payment type incompatible with this mode, a 400 error will be returned.  A merchant would need to perform their own capture via API where applicable.<br><br><br>- CAPTURE: Use this value when you want to perform a sale within Unified Checkout and capture the payment immediately during the transaction.  Note: Some payment types may return a PENDING status, requiring an additional status check call to determine the final outcome of the payment.<br><br><br>- PREFER_AUTH: Use this value to offer multiple alternative payment options during the Unified Checkout experience. This option authorizes the payment without immediate capture, where available.  It will perform a "CAPTURE" where an "AUTH" is not allowed by the payment type.  Transactions can be AUTHORIZED, CAPTURED, or PENDING.  If an "AUTH" is performed, a merchant would need to perform their own capture via API where applicable.<br><br>**Constraints**: *Maximum Length*: `25` | getType(): ?string | setType(?string type): void |
| `decisionManager` | `?bool` | Optional | Configure Unified Checkout to determine whether Decision Manager is invoked during service orchestration.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>Setting this value to True indicates that device fingerprinting will be executed to add additional information for risk service<br>Setting this value to False (or not provided) indicates that you do not wish to run device fingerprinting and skip decision manager services. | getDecisionManager(): ?bool | setDecisionManager(?bool decisionManager): void |
| `consumerAuthentication` | `?bool` | Optional | Configure Unified Checkout to determine whether Consumer Authentication is invoked during service orchestration.<br><br>Possible values:<br><br>- True<br>- False<br><br><br><br>Setting this value to True will attempt to perform authentication using the Payer Authentication Service.<br>Setting this value to False (or not provided) indicates that you do not wish to perform authentication using the Payer Authentication Service. | getConsumerAuthentication(): ?bool | setConsumerAuthentication(?bool consumerAuthentication): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\CompleteMandate2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$completeMandate2 = CompleteMandate2Builder::init()
    ->type('AUTH')
    ->decisionManager(false)
    ->consumerAuthentication(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

