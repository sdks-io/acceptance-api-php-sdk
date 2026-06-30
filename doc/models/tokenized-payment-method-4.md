
# Tokenized Payment Method 4

*This model accepts additional fields of type array.*

## Structure

`TokenizedPaymentMethod4`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?string` | Optional | The PayPal-generated ID for the token.<br><br>**Constraints**: *Maximum Length*: `255` | getId(): ?string | setId(?string id): void |
| `usageType` | `?string` | Optional | Indicates the type of vaulting relationship. Valid values:<br><br>- “MERCHANT”: Single merchant relationship.<br>- “PLATFORM”: Platform hosting multiple merchants.<br><br>**Constraints**: *Maximum Length*: `255` | getUsageType(): ?string | setUsageType(?string usageType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\TokenizedPaymentMethod4Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$tokenizedPaymentMethod4 = TokenizedPaymentMethod4Builder::init()
    ->id('id6')
    ->usageType('usageType4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

