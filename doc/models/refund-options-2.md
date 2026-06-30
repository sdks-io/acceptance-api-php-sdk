
# Refund Options 2

*This model accepts additional fields of type array.*

## Structure

`RefundOptions2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `reason` | `?string` | Optional | Must be set to `pow` for Mastercard Gaming Payment of Winnings tranactions. | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RefundOptions2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$refundOptions2 = RefundOptions2Builder::init()
    ->reason('reason2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

