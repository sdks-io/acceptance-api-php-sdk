
# Recurring Options

*This model accepts additional fields of type array.*

## Structure

`RecurringOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loanPayment` | `?bool` | Optional | Flag that indicates whether this is a payment towards an existing contractual loan.<br><br>Possible values:<br><br>- `true`: Loan payment<br>- `false`: (default) Not a loan payment<br><br>**Default**: `false` | getLoanPayment(): ?bool | setLoanPayment(?bool loanPayment): void |
| `firstRecurringPayment` | `?bool` | Optional | Flag that indicates whether this transaction is the first in a series of recurring payments.<br><br>This field is supported only for **Atos**, **FDC Nashville Global**, and **OmniPay Direct**.<br><br>Possible values:<br><br>- `true` Indicates this is the first payment in a series of recurring payments<br>- `false` (default) Indicates this is not the first payment in a series of recurring payments.<br><br>**Default**: `false` | getFirstRecurringPayment(): ?bool | setFirstRecurringPayment(?bool firstRecurringPayment): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecurringOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recurringOptions = RecurringOptionsBuilder::init()
    ->loanPayment(false)
    ->firstRecurringPayment(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

