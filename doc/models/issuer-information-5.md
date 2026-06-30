
# Issuer Information 5

*This model accepts additional fields of type array.*

## Structure

`IssuerInformation5`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `?string` | Optional | Name of the card issuer provided by the processor.<br><br>**Constraints**: *Maximum Length*: `20` | getName(): ?string | setName(?string name): void |
| `code` | `?string` | Optional | Unique code for card issuer provided by the processor.<br><br>**Constraints**: *Maximum Length*: `10` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\IssuerInformation5Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$issuerInformation5 = IssuerInformation5Builder::init()
    ->name('name4')
    ->code('code2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

