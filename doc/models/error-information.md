
# Error Information

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- AVS_FAILED<br>- CONTACT_PROCESSOR<br>- EXPIRED_CARD<br>- PROCESSOR_DECLINED<br>- INSUFFICIENT_FUND<br>- STOLEN_LOST_CARD<br>- ISSUER_UNAVAILABLE<br>- UNAUTHORIZED_CARD<br>- CVN_NOT_MATCH<br>- EXCEEDS_CREDIT_LIMIT<br>- INVALID_CVN<br>- BLOCKED_BY_CARDHOLDER<br>- DECLINED_CHECK<br>- BLACKLISTED_CUSTOMER<br>- SUSPENDED_ACCOUNT<br>- PAYMENT_REFUSED<br>- CV_FAILED<br>- INVALID_ACCOUNT<br>- GENERAL_DECLINE<br>- INVALID_MERCHANT_CONFIGURATION<br>- DECISION_PROFILE_REJECT<br>- SCORE_EXCEEDS_THRESHOLD<br>- PENDING_AUTHENTICATION<br>- ACH_VERIFICATION_FAILED<br>- DECISION_PROFILE_REVIEW<br>- CONSUMER_AUTHENTICATION_REQUIRED<br>- CONSUMER_AUTHENTICATION_FAILED<br>- ALLOWABLE_PIN_RETRIES_EXCEEDED<br>- PROCESSOR_ERROR<br>- CUSTOMER_WATCHLIST_MATCH<br>- ADDRESS_COUNTRY_WATCHLIST_MATCH<br>- EMAIL_COUNTRY_WATCHLIST_MATCH<br>- IP_COUNTRY_WATCHLIST_MATCH<br>- INVALID_MERCHANT_CONFIGURATION | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail[])`](../../doc/models/detail.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DetailBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation = ErrorInformationBuilder::init()
    ->reason('reason4')
    ->message('message8')
    ->details(
        [
            DetailBuilder::init()
                ->field('field4')
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

