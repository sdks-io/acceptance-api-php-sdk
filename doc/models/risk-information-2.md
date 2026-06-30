
# Risk Information 2

*This model accepts additional fields of type array.*

## Structure

`RiskInformation2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `processorResults` | [`?ProcessorResults1`](../../doc/models/processor-results-1.md) | Optional | - | getProcessorResults(): ?ProcessorResults1 | setProcessorResults(?ProcessorResults1 processorResults): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RiskInformation2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorResults1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$riskInformation2 = RiskInformation2Builder::init()
    ->processorResults(
        ProcessorResults1Builder::init()
            ->riskScore('riskScore4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

