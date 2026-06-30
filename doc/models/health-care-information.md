
# Health Care Information

*This model accepts additional fields of type array.*

## Structure

`HealthCareInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountDetails` | [`?(AmountDetails1[])`](../../doc/models/amount-details-1.md) | Optional | array for Healthcare fields | getAmountDetails(): ?array | setAmountDetails(?array amountDetails): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\HealthCareInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$healthCareInformation = HealthCareInformationBuilder::init()
    ->amountDetails(
        [
            AmountDetails1Builder::init()
                ->amountType('amountType2')
                ->amount('amount2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            AmountDetails1Builder::init()
                ->amountType('amountType2')
                ->amount('amount2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build(),
            AmountDetails1Builder::init()
                ->amountType('amountType2')
                ->amount('amount2')
                ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->build()
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

