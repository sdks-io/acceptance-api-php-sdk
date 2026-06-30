
# Options 1

*This model accepts additional fields of type array.*

## Structure

`Options1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | Identifier for a PayPal credit transaction.<br>Value: Credit<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Options1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$options1 = Options1Builder::init()
    ->id('id6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

