
# Tokenized Payment Method 1

*This model accepts additional fields of type array.*

## Structure

`TokenizedPaymentMethod1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The PayPal-generated ID for the token.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `status` | `?string` | Optional | The vault status.<br>Possible Values:<br><br>- `VAULTED`<br>- `CREATED`<br>- `APPROVED`<br><br>**Constraints**: *Maximum Length*: `255` | getStatus(): ?string | setStatus(?string status): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenizedPaymentMethod1 = TokenizedPaymentMethod1Builder::init()
    ->id('id2')
    ->status('status4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

