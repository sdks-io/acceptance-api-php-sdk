
# Processing Information 6

*This model accepts additional fields of type array.*

## Structure

`ProcessingInformation6`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `enhancedDataEnabled` | `?bool` | Optional | The possible values for the reply field are:<br><br>- `true` : the airline data was included in the request to the processor.<br>- `false` : the airline data was not included in the request to the processor.<br><br>Returned by authorization, capture, or credit services. | getEnhancedDataEnabled(): ?bool | setEnhancedDataEnabled(?bool enhancedDataEnabled): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ProcessingInformation6Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$processingInformation6 = ProcessingInformation6Builder::init()
    ->enhancedDataEnabled(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

