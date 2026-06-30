
# Bank 11

*This model accepts additional fields of type array.*

## Structure

`Bank11`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `swiftCode` | `?string` | Optional | Bank’s SWIFT code. You can use this field only when scoring a direct debit transaction.<br>Required only for crossborder transactions. | getSwiftCode(): ?string | setSwiftCode(?string swiftCode): void |
| `account` | [`?Account12`](../../doc/models/account-12.md) | Optional | - | getAccount(): ?Account12 | setAccount(?Account12 account): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Bank11Builder;
use VisaAcceptanceMergedSpecLib\Models\Builders\Account12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bank11 = Bank11Builder::init()
    ->swiftCode('swiftCode4')
    ->account(
        Account12Builder::init()
            ->number('number8')
            ->iban('iban4')
            ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->build()
    )
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

