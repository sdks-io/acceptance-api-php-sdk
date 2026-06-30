
# Account 12

*This model accepts additional fields of type array.*

## Structure

`Account12`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `number` | `?string` | Optional | Account number.<br><br>When processing encoded account numbers, use this field for the encoded account number.<br><br>**Constraints**: *Maximum Length*: `17` | getNumber(): ?string | setNumber(?string number): void |
| `iban` | `?string` | Optional | International Bank Account Number (IBAN) for the bank account. For some countries you can provide this number instead of the traditional bank account information. You can use this field only when scoring a direct debit transaction.<br><br>**Constraints**: *Maximum Length*: `50` | getIban(): ?string | setIban(?string iban): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\Account12Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$account12 = Account12Builder::init()
    ->number('number6')
    ->iban('iban0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

