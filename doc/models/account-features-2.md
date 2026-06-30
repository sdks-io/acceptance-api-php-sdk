
# Account Features 2

*This model accepts additional fields of type array.*

## Structure

`AccountFeatures2`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `balanceAmount` | `?string` | Optional | Remaining balance on the account.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Remaining balance on the prepaid card.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `12` | getBalanceAmount(): ?string | setBalanceAmount(?string balanceAmount): void |
| `previousBalanceAmount` | `?string` | Optional | Remaining balance on the account.<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Remaining balance on the prepaid card.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `12` | getPreviousBalanceAmount(): ?string | setPreviousBalanceAmount(?string previousBalanceAmount): void |
| `currency` | `?string` | Optional | Currency of the remaining balance on the account. For the possible values, see the [ISO Standard Currency Codes.](<br><br>Returned by authorization service.<br><br>#### PIN debit<br><br>Currency of the remaining balance on the prepaid card.<br><br>Returned by PIN debit purchase.<br><br>**Constraints**: *Maximum Length*: `5` | getCurrency(): ?string | setCurrency(?string currency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AccountFeatures2Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$accountFeatures2 = AccountFeatures2Builder::init()
    ->balanceAmount('balanceAmount0')
    ->previousBalanceAmount('previousBalanceAmount2')
    ->currency('currency8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

