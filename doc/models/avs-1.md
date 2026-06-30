
# Avs 1

*This model accepts additional fields of type array.*

## Structure

`Avs1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `codeRaw` | `?string` | Optional | AVS result code sent directly from the processor. Returned only when the processor returns this value.<br>**Important** Do not use this field to evaluate the result of AVS. Use for debugging purposes only.<br><br>Returned by authorization service.<br><br>**Constraints**: *Maximum Length*: `10` | getCodeRaw(): ?string | setCodeRaw(?string codeRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Avs1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$avs1 = Avs1Builder::init()
    ->codeRaw('codeRaw8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

