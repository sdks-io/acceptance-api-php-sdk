
# Issuer 1

*This model accepts additional fields of type array.*

## Structure

`Issuer1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional, Read-only | issuer name. | getName(): ?string | setName(?string name): void |
| `shortDescription` | `?string` | Optional, Read-only | issuer short description. | getShortDescription(): ?string | setShortDescription(?string shortDescription): void |
| `longDescription` | `?string` | Optional, Read-only | issuer long  description. | getLongDescription(): ?string | setLongDescription(?string longDescription): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Issuer1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuer1 = Issuer1Builder::init()
    ->name('name8')
    ->shortDescription('shortDescription6')
    ->longDescription('longDescription8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

