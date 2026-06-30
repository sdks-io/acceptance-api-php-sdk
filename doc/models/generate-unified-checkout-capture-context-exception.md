
# Generate Unified Checkout Capture Context Exception

*This model accepts additional fields of type array.*

## Structure

`GenerateUnifiedCheckoutCaptureContextException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `correlationId` | `?string` | Optional | - | getCorrelationId(): ?string | setCorrelationId(?string correlationId): void |
| `details` | [`?(Detail66[])`](../../doc/models/detail-66.md) | Optional | - | getDetails(): ?array | setDetails(?array details): void |
| `informationLink` | `?string` | Optional | - | getInformationLink(): ?string | setInformationLink(?string informationLink): void |
| `message` | `string` | Required | - | getMessage(): string | setMessage(string message): void |
| `reason` | [`string(Reason)`](../../doc/models/reason.md) | Required | - | getReason(): string | setReason(string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\GenerateUnifiedCheckoutCaptureContextExceptionBuilder;
use VisaAcceptanceMergedSpecLib\Models\Reason;
use VisaAcceptanceMergedSpecLib\Models\Builders\Detail66Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$generateUnifiedCheckoutCaptureContextException = GenerateUnifiedCheckoutCaptureContextExceptionBuilder::init(
    'message0',
    Reason::SDK_XHR_ERROR
)
    ->correlationId('correlationId0')
    ->details(
        [
            Detail66Builder::init()
                ->location('location4')
                ->message('message0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail66Builder::init()
                ->location('location4')
                ->message('message0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            Detail66Builder::init()
                ->location('location4')
                ->message('message0')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->informationLink('informationLink8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

