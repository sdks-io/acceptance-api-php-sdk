
# Bank Account Validation

*This model accepts additional fields of type array.*

## Structure

`BankAccountValidation`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `rawValidationCode` | `?int` | Optional | Raw Validation Codes for routing number and account number<br><br>    Possible values:<br>    • -1: Unable to perform validation/Unknown error<br>    • -2: Service Unavailable<br>    • 12 to 16: Validation results | getRawValidationCode(): ?int | setRawValidationCode(?int rawValidationCode): void |
| `resultCode` | `?int` | Optional | Result codes for account number and routing number<br><br>    Possible values: 00, 04, 98, 99 | getResultCode(): ?int | setResultCode(?int resultCode): void |
| `resultMessage` | `?string` | Optional | - | getResultMessage(): ?string | setResultMessage(?string resultMessage): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankAccountValidationBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankAccountValidation = BankAccountValidationBuilder::init()
    ->rawValidationCode(124)
    ->resultCode(46)
    ->resultMessage('resultMessage2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

