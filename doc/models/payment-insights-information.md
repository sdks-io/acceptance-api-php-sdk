
# Payment Insights Information

*This model accepts additional fields of type array.*

## Structure

`PaymentInsightsInformation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `responseInsights` | [`?ResponseInsights`](../../doc/models/response-insights.md) | Optional | - | getResponseInsights(): ?ResponseInsights | setResponseInsights(?ResponseInsights responseInsights): void |
| `orchestration` | [`?Orchestration`](../../doc/models/orchestration.md) | Optional | - | getOrchestration(): ?Orchestration | setOrchestration(?Orchestration orchestration): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PaymentInsightsInformationBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ResponseInsightsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;
use VisaAcceptanceMergedSpecLib\Models\Builders\OrchestrationBuilder;

$paymentInsightsInformation = PaymentInsightsInformationBuilder::init()
    ->responseInsights(
        ResponseInsightsBuilder::init()
            ->category('category2')
            ->categoryCode('categoryCode4')
            ->processorRawName('processorRawName4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->orchestration(
        OrchestrationBuilder::init()
            ->infoCodes(
                [
                    'infoCodes0'
                ]
            )
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

