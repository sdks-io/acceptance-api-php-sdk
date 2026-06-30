
# Recurring Options 1

*This model accepts additional fields of type array.*

## Structure

`RecurringOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loanPayment` | `?bool` | Optional | Flag that indicates whether this is a payment towards an existing contractual loan.<br><br>Possible values:<br><br>- `true`: Loan payment<br>- `false`: (default) Not a loan payment<br><br>**Default**: `false` | getLoanPayment(): ?bool | setLoanPayment(?bool loanPayment): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecurringOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recurringOptions1 = RecurringOptions1Builder::init()
    ->loanPayment(false)
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

