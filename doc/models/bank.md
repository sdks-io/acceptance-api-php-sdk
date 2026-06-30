
# Bank

*This model accepts additional fields of type array.*

## Structure

`Bank`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account`](../../doc/models/account.md) | Optional | - | getAccount(): ?Account | setAccount(?Account account): void |
| `routingNumber` | `?string` | Optional | Bank routing number. This is also called the _transit number_.<br><br>**Constraints**: *Maximum Length*: `9` | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN) for the bank account. For some countries you can provide this number instead of the traditional bank account information. You can use this field only when scoring a direct debit transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getIban(): ?string | setIban(?string iban): void |
| `swiftCode` | `?string` | Optional | Bank’s SWIFT code. You can use this field only when scoring a direct debit transaction.<br>Required only for crossborder transactions. | getSwiftCode(): ?string | setSwiftCode(?string swiftCode): void |
| `code` | `?string` | Optional | Bank code of the consumer’s account<br><br>**Constraints**: *Maximum Length*: `50` | getCode(): ?string | setCode(?string code): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankBuilder;
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank = BankBuilder::init()
    ->account(
        AccountBuilder::init()
            ->type('type0')
            ->number('number8')
            ->encoderId('encoderId4')
            ->checkNumber('checkNumber6')
            ->checkImageReferenceNumber('checkImageReferenceNumber2')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->routingNumber('routingNumber0')
    ->iban('iban2')
    ->swiftCode('swiftCode0')
    ->code('code6')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

