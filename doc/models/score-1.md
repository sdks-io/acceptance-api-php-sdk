
# Score 1

*This model accepts additional fields of type array.*

## Structure

`Score1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `factorCodes` | `?(string[])` | Optional | Array of factor codes. | getFactorCodes(): ?array | setFactorCodes(?array factorCodes): void |
| `result` | `?int` | Optional | The description for this field is not available. | getResult(): ?int | setResult(?int result): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Score1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$score1 = Score1Builder::init()
    ->factorCodes(
        [
            'factorCodes8',
            'factorCodes9',
            'factorCodes0'
        ]
    )
    ->result(76)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

