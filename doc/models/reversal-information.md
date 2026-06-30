
# Reversal Information

*This model accepts additional fields of type array.*

## Structure

`ReversalInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?AmountDetails5`](../../doc/models/amount-details-5.md) | Optional | - | getAmountDetails(): ?AmountDetails5 | setAmountDetails(?AmountDetails5 amountDetails): void |
| `reason` | `?string` | Optional | Reason for the authorization reversal. Possible value:<br><br>- `34`: Suspected fraud<br><br>This field is ignored for processors that do not support this value.<br><br>Returned by authorization reversal. | getReason(): ?string | setReason(?string reason): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ReversalInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$reversalInformation = ReversalInformationBuilder::init()
    ->amountDetails(
        AmountDetails5Builder::init()
            ->totalAmount('totalAmount4')
            ->currency('currency0')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->reason('reason4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

