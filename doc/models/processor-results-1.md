
# Processor Results 1

*This model accepts additional fields of type array.*

## Structure

`ProcessorResults1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `riskScore` | `?string` | Optional | Risk score returned by the processor. Possible<br>values of 0-10. A value of 10 indicates a high risk.<br><br>**Constraints**: *Maximum Length*: `25` | getRiskScore(): ?string | setRiskScore(?string riskScore): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessorResults1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processorResults1 = ProcessorResults1Builder::init()
    ->riskScore('riskScore0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

