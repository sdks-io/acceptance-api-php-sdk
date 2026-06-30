
# Orchestration

*This model accepts additional fields of type array.*

## Structure

`Orchestration`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `infoCodes` | `?(string[])` | Optional | Infocodes indicating which rules were triggered by the Service Orchestration product.<br><br>**Constraints**: *Maximum Length*: `60` | getInfoCodes(): ?array | setInfoCodes(?array infoCodes): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\OrchestrationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$orchestration = OrchestrationBuilder::init()
    ->infoCodes(
        [
            'infoCodes0'
        ]
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

