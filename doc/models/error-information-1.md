
# Error Information 1

*This model accepts additional fields of type array.*

## Structure

`ErrorInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | The reason of the status.<br><br>Possible values:<br><br>- AVS_FAILED<br>- CONTACT_PROCESSOR<br>- EXPIRED_CARD<br>- PROCESSOR_DECLINED<br>- INSUFFICIENT_FUND<br>- STOLEN_LOST_CARD<br>- ISSUER_UNAVAILABLE<br>- UNAUTHORIZED_CARD<br>- CVN_NOT_MATCH<br>- EXCEEDS_CREDIT_LIMIT<br>- INVALID_CVN<br>- BLOCKED_BY_CARDHOLDER<br>- BLACKLISTED_CUSTOMER<br>- SUSPENDED_ACCOUNT<br>- PAYMENT_REFUSED<br>- CV_FAILED<br>- INVALID_ACCOUNT<br>- GENERAL_DECLINE<br>- INVALID_MERCHANT_CONFIGURATION<br>- DECISION_PROFILE_REJECT<br>- SCORE_EXCEEDS_THRESHOLD<br>- CONSUMER_AUTHENTICATION_REQUIRED<br>- ALLOWABLE_PIN_RETRIES_EXCEEDED<br>- PROCESSOR_ERROR | getReason(): ?string | setReason(?string reason): void |
| `message` | `?string` | Optional | The detail message related to the status and reason listed above. | getMessage(): ?string | setMessage(?string message): void |
| `details` | [`?(Detail[])`](../../doc/models/detail.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ErrorInformation1Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\DetailBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$errorInformation1 = ErrorInformation1Builder::init()
    ->reason('reason2')
    ->message('message6')
    ->details(
        [
            DetailBuilder::init()
                ->field('field4')
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            DetailBuilder::init()
                ->field('field4')
                ->reason('reason6')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
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

