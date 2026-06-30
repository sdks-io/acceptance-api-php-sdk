
# Account 8

*This model accepts additional fields of type array.*

## Structure

`Account8`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ibanSuffix` | `?string` | Optional | The description for this field is not available. | getIbanSuffix(): ?string | setIbanSuffix(?string ibanSuffix): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account8Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account8 = Account8Builder::init()
    ->ibanSuffix('ibanSuffix0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

