
# Bank 7

*This model accepts additional fields of type array.*

## Structure

`Bank7`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account9`](../../doc/models/account-9.md) | Optional | - | getAccount(): ?Account9 | setAccount(?Account9 account): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN).<br><br>#### SEPA<br><br>Required for mandates services<br><br>**Constraints**: *Maximum Length*: `34` | getIban(): ?string | setIban(?string iban): void |
| `swiftCode` | `?string` | Optional | Bank’s SWIFT code. You can use this field only when scoring a direct debit transaction.<br><br>#### BACS<br><br>Required for mandates services<br><br>**Constraints**: *Maximum Length*: `20` | getSwiftCode(): ?string | setSwiftCode(?string swiftCode): void |
| `scheme` | `?string` | Optional | The scheme that sets the rules for the direct<br>debit process. Possible values:<br><br>- SEPA<br>- BACS<br><br>#### SEPA/BACS<br><br>Required for mandates services<br><br>**Constraints**: *Maximum Length*: `25` | getScheme(): ?string | setScheme(?string scheme): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank7Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account9Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank7 = Bank7Builder::init()
    ->account(
        Account9Builder::init()
            ->number('number8')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->iban('iban0')
    ->swiftCode('swiftCode2')
    ->scheme('scheme6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

