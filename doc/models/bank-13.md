
# Bank 13

*This model accepts additional fields of type array.*

## Structure

`Bank13`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `routingNumber` | `?string` | Optional | Bank routing number. This is also called the transit number. | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |
| `branchCode` | `?string` | Optional | Code used to identify the branch of the customer’s bank.<br>Required for some countries if you do not or are not<br>allowed to provide the IBAN. Use this field only when<br>scoring a direct debit transaction. | getBranchCode(): ?string | setBranchCode(?string branchCode): void |
| `swiftCode` | `?string` | Optional | Bank’s SWIFT code. You can use this field only when scoring a direct debit transaction.<br>Required only for crossborder transactions. | getSwiftCode(): ?string | setSwiftCode(?string swiftCode): void |
| `bankCode` | `?string` | Optional | Country-specific code used to identify the customer’s<br>bank. Required for some countries if you do not or are not<br>allowed to provide the IBAN instead. You can use this field<br>only when scoring a direct debit transaction. | getBankCode(): ?string | setBankCode(?string bankCode): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN) for the bank account. For some countries you can provide this number instead of the traditional bank account information. You can use this field only when scoring a direct debit transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getIban(): ?string | setIban(?string iban): void |
| `account` | [`?Account15`](../../doc/models/account-15.md) | Optional | - | getAccount(): ?Account15 | setAccount(?Account15 account): void |
| `mandate` | [`?Mandate1`](../../doc/models/mandate-1.md) | Optional | - | getMandate(): ?Mandate1 | setMandate(?Mandate1 mandate): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank13Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank13 = Bank13Builder::init()
    ->routingNumber('routingNumber8')
    ->branchCode('branchCode2')
    ->swiftCode('swiftCode2')
    ->bankCode('bankCode6')
    ->iban('iban0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

