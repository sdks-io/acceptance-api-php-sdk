
# Consumer Authentication Response

*This model accepts additional fields of type array.*

## Structure

`ConsumerAuthenticationResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `code` | `?string` | Optional | Mapped response code for Visa Secure and American Express SafeKey.<br><br>**Constraints**: *Maximum Length*: `3` | getCode(): ?string | setCode(?string code): void |
| `codeRaw` | `?string` | Optional | Raw response code sent directly from the processor for Visa Secure and American Express SafeKey:<br><br>**Constraints**: *Maximum Length*: `3` | getCodeRaw(): ?string | setCodeRaw(?string codeRaw): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\ConsumerAuthenticationResponseBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$consumerAuthenticationResponse = ConsumerAuthenticationResponseBuilder::init()
    ->code('code0')
    ->codeRaw('codeRaw2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

