
# Tokenized Payment Method

*This model accepts additional fields of type array.*

## Structure

`TokenizedPaymentMethod`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The PayPal-generated ID for the token.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethodBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenizedPaymentMethod = TokenizedPaymentMethodBuilder::init()
    ->id('id0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

