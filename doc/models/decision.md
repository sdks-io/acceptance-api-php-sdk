
# Decision

*This model accepts additional fields of type array.*

## Structure

`Decision`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `status` | `?string` | Optional | The status of the submitted transaction.<br><br>Possible values:<br><br>- `ACCEPTED`<br>- `REJECTED`<br>- `PENDING_REVIEW`<br>- `DECLINED`<br>- `PENDING_AUTHENTICATION`<br>- `INVALID_REQUEST`<br>- `AUTHENTICATION_FAILED`<br>- `CHALLENGE` | getStatus(): ?string | setStatus(?string status): void |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- `EXPIRED_CARD`<br>- `SCORE_EXCEEDS_THRESHOLD`<br>- `DECISION_PROFILE_REVIEW`<br>- `DECISION_PROFILE_REJECT`<br>- `CONSUMER_AUTHENTICATION_REQUIRED`<br>- `INVALID_MERCHANT_CONFIGURATION`<br>- `CONSUMER_AUTHENTICATION_FAILED`<br>- `DECISION_PROFILE_CHALLENGE`<br>- `CUSTOMER_WATCHLIST_MATCH`<br>- `ADDRESS_COUNTRY_WATCHLIST_MATCH`<br>- `EMAIL_COUNTRY_WATCHLIST_MATCH`<br>- `IP_COUNTRY_WATCHLIST_MATCH` | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\DecisionBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$decision = DecisionBuilder::init()
    ->status('status4')
    ->reason('reason8')
    ->message('message2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

