
# Bank Account

*This model accepts additional fields of type array.*

## Structure

`BankAccount`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `type` | `?string` | Optional | Account type.<br><br>Possible Values:<br><br>- checking : C<br>- general ledger : G This value is supported only on Wells Fargo ACH<br>- savings : S (U.S. dollars only)<br>- corporate checking : X (U.S. dollars only)<br><br>**Constraints**: *Maximum Length*: `18` | getType(): ?string | setType(?string type): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BankAccountBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$bankAccount = BankAccountBuilder::init()
    ->type('type2')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

