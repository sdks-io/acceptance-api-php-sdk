
# Issuer 3

Issuer associated with the tokenized card.

*This model accepts additional fields of type array.*

## Structure

`Issuer3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional, Read-only | issuer name. | getName(): ?string | setName(?string name): void |
| `shortDescription` | `?string` | Optional, Read-only | issuer short description. | getShortDescription(): ?string | setShortDescription(?string shortDescription): void |
| `longDescription` | `?string` | Optional, Read-only | issuer long  description. | getLongDescription(): ?string | setLongDescription(?string longDescription): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Issuer3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuer3 = Issuer3Builder::init()
    ->name('name6')
    ->shortDescription('shortDescription8')
    ->longDescription('longDescription6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

