
# Bank 2

*This model accepts additional fields of type array.*

## Structure

`Bank2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `account` | [`?Account3`](../../doc/models/account-3.md) | Optional | - | getAccount(): ?Account3 | setAccount(?Account3 account): void |
| `routingNumber` | `?string` | Optional | Bank routing number. This is also called the _transit number_.<br><br>**Constraints**: *Maximum Length*: `9` | getRoutingNumber(): ?string | setRoutingNumber(?string routingNumber): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN) for the bank account. For some countries you can provide this number instead of the traditional bank account information. You can use this field only when scoring a direct debit transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getIban(): ?string | setIban(?string iban): void |
| `swiftCode` | `?string` | Optional | Bank’s SWIFT code. You can use this field only when scoring a direct debit transaction.<br>Required only for crossborder transactions. | getSwiftCode(): ?string | setSwiftCode(?string swiftCode): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank2Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account3Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank2 = Bank2Builder::init()
    ->account(
        Account3Builder::init()
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
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

