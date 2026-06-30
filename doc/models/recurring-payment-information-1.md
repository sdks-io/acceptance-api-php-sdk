
# Recurring Payment Information 1

*This model accepts additional fields of type array.*

## Structure

`RecurringPaymentInformation1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountType` | `?string` | Optional | Indicates recurring amount type agreed by the cardholder<br>Valid Values :<br>1- Fixed amount recurring payment<br>2- Recurring payment with maximum amount<br><br>**Constraints**: *Maximum Length*: `1` | getAmountType(): ?string | setAmountType(?string amountType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\RecurringPaymentInformation1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$recurringPaymentInformation1 = RecurringPaymentInformation1Builder::init()
    ->amountType('amountType0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

