
# Account

*This model accepts additional fields of type array.*

## Structure

`Account`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Account type.<br><br>Possible values:<br><br>- **C**: Checking.<br>- **G**: General ledger. This value is supported only on Wells Fargo ACH.<br>- **S**: Savings (U.S. dollars only).<br>- **X**: Corporate checking (U.S. dollars only).<br><br>**Constraints**: *Maximum Length*: `1` | getType(): ?string | setType(?string type): void |
| `number` | `?string` | Optional | Account number.<br><br>When processing encoded account numbers, use this field for the encoded account number.<br><br>**Constraints**: *Maximum Length*: `17` | getNumber(): ?string | setNumber(?string number): void |
| `encoderId` | `?string` | Optional | Identifier for the bank that provided the customer’s encoded account number.<br><br>To obtain the bank identifier, contact your processor.<br><br>**Constraints**: *Maximum Length*: `3` | getEncoderId(): ?string | setEncoderId(?string encoderId): void |
| `checkNumber` | `?string` | Optional | Check number.<br><br>Chase Paymentech Solutions - Optional.<br>Visa Acceptance ACH Service - Not used.<br>RBS WorldPay Atlanta - Optional on debits. Required on credits.<br>TeleCheck - Strongly recommended on debit requests. Optional on credits.<br><br>**Constraints**: *Maximum Length*: `8` | getCheckNumber(): ?string | setCheckNumber(?string checkNumber): void |
| `checkImageReferenceNumber` | `?string` | Optional | Image reference number associated with the check. You cannot include any special characters.<br><br>**Constraints**: *Maximum Length*: `32` | getCheckImageReferenceNumber(): ?string | setCheckImageReferenceNumber(?string checkImageReferenceNumber): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN) for the bank account. For some countries you can provide this number instead of the traditional bank account information. You can use this field only when scoring a direct debit transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getIban(): ?string | setIban(?string iban): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account = AccountBuilder::init()
    ->type('type0')
    ->number('number8')
    ->encoderId('encoderId4')
    ->checkNumber('checkNumber6')
    ->checkImageReferenceNumber('checkImageReferenceNumber2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

