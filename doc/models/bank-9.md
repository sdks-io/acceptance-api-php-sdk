
# Bank 9

*This model accepts additional fields of type array.*

## Structure

`Bank9`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN).<br><br>**Constraints**: *Maximum Length*: `34` | getIban(): ?string | setIban(?string iban): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank9 = Bank9Builder::init()
    ->iban('iban6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

