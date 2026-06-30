
# Passcode

Passcode by issuer for ID&V.

*This model accepts additional fields of type array.*

## Structure

`Passcode`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `value` | `?string` | Optional | OTP generated at issuer. | getValue(): ?string | setValue(?string value): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PasscodeBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$passcode = PasscodeBuilder::init()
    ->value('value6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

