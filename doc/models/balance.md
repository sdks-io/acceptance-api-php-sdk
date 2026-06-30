
# Balance

*This model accepts additional fields of type array.*

## Structure

`Balance`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `accountType` | `?string` | Optional | Type of account.<br><br>This value is returned only if you request a balance inquiry.<br><br>Possible values:<br><br>- `00`: Not applicable or not specified<br>- `10`: Savings account<br>- `20`: Checking account<br>- `30`: Credit card account<br>- `40`: Universal account<br><br>Balance Account Types returned on EBT Debit card transactions:<br><br>- `96`: Cash Benefits Account (PIN Debit Gateway EBT only)<br>- `98`: Food Stamp Account (PIN Debit Gateway EBT only)<br><br>**Constraints**: *Maximum Length*: `2` | getAccountType(): ?string | setAccountType(?string accountType): void |
| `amount` | `?string` | Optional | Remaining balance on the account. If the processor returns the sign, positive or negative, this sign is prefixed<br>to the amount value as (+/-).<br><br>**Constraints**: *Maximum Length*: `13` | getAmount(): ?string | setAmount(?string amount): void |
| `amountType` | `?string` | Optional | Type of amount. This value is returned only if you request a balance inquiry. The issuer determines the value<br>that is returned.<br><br>Possible values for deposit accounts:<br><br>- `01`: Current ledger (posted) balance.<br>- `02`: Current available balance, which is typically the ledger balance minus outstanding authorizations. Some<br>  depository institutions also include pending deposits and the credit or overdraft line associated with the account.<br><br>Possible values for credit card accounts:<br><br>- `01`: Credit amount remaining for customer (open to buy).<br>- `02`: Credit limit.<br><br>**Constraints**: *Maximum Length*: `2` | getAmountType(): ?string | setAmountType(?string amountType): void |
| `currency` | `?string` | Optional | Currency of the remaining balance on the account.<br><br>**Constraints**: *Maximum Length*: `3` | getCurrency(): ?string | setCurrency(?string currency): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\BalanceBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$balance = BalanceBuilder::init()
    ->accountType('accountType4')
    ->amount('amount6')
    ->amountType('amountType6')
    ->currency('currency4')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

