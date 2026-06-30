
# Account 15

*This model accepts additional fields of type array.*

## Structure

`Account15`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `suffix` | `?string` | Optional | Last four digits of the customer’s payment account number. | getSuffix(): ?string | setSuffix(?string suffix): void |
| `prefix` | `?string` | Optional | Bank Identification Number (BIN). This is the initial four to six numbers on a credit card account number. | getPrefix(): ?string | setPrefix(?string prefix): void |
| `checkNumber` | `?string` | Optional | Check number.<br><br>Chase Paymentech Solutions - Optional.<br>Visa Acceptance ACH Service - Not used.<br>RBS WorldPay Atlanta - Optional on debits. Required on credits.<br>TeleCheck - Strongly recommended on debit requests. Optional on credits.<br><br>**Constraints**: *Maximum Length*: `8` | getCheckNumber(): ?string | setCheckNumber(?string checkNumber): void |
| `type` | `?string` | Optional | Account type.<br><br>Possible values:<br><br>- **C**: Checking.<br>- **G**: General ledger. This value is supported only on Wells Fargo ACH.<br>- **S**: Savings (U.S. dollars only).<br>- **X**: Corporate checking (U.S. dollars only).<br><br>**Constraints**: *Maximum Length*: `1` | getType(): ?string | setType(?string type): void |
| `name` | `?string` | Optional | Name used on the bank account. You can use this field only when scoring a direct debit transaction | getName(): ?string | setName(?string name): void |
| `checkDigit` | `?string` | Optional | Code used to validate the customer’s account number.<br>Required for some countries if you do not or are not<br>allowed to provide the IBAN instead. You may use this<br>field only when scoring a direct debit transaction. | getCheckDigit(): ?string | setCheckDigit(?string checkDigit): void |
| `encoderId` | `?string` | Optional | Identifier for the bank that provided the customer’s encoded account number.<br><br>To obtain the bank identifier, contact your processor.<br><br>**Constraints**: *Maximum Length*: `3` | getEncoderId(): ?string | setEncoderId(?string encoderId): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account15Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account15 = Account15Builder::init()
    ->suffix('suffix8')
    ->prefix('prefix6')
    ->checkNumber('checkNumber4')
    ->type('type8')
    ->name('name8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

