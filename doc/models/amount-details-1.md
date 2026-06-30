
# Amount Details 1

*This model accepts additional fields of type array.*

## Structure

`AmountDetails1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `amountType` | `?string` | Optional | Total amount that has been spent on healthcare in a transaction.<br>Valid Values for **Visa**:<br><br>- `healthcare` - Total Amount Healthcare<br>- `healthcare-transit` - Amount Transit<br>- `vision` - Amount Vision/Optical<br>- `prescription` - Amount Prescription/RX<br>- `clinic` - Amount Clinic/Other Qualified Medical<br>- `dental` - Amount Dental<br><br>`Note:` -  Prescription, Clinic and dental amounts must be preceded with the total healthcare amount and cannot occur individually.  Vision and Transit must be sent individually and cannot be combined with total healthcare amount or any other amounts. Total Healthcare amount can be sent individually.<br><br>Valid Values for **MasterCard**:<br><br>- `prescription` - Amount Prescription/RX<br>- `eligible-total` - Total Amount Healthcare<br><br>`Note:` -  Prescription must be preceded with the total healthcare amount and cannot occur individually. Total Healthcare amount can be sent individually.<br><br>**Constraints**: *Maximum Length*: `35` | getAmountType(): ?string | setAmountType(?string amountType): void |
| `amount` | `?string` | Optional | Total Amount that has been spent on the corresponding amountType. This is 13 byte field including sign.<br>If the amount is positive, then it is a debit for the customer.<br>If the amount is negative, then it is a credit for the customer.<br><br>**Constraints**: *Maximum Length*: `13` | getAmount(): ?string | setAmount(?string amount): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\AmountDetails1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$amountDetails1 = AmountDetails1Builder::init()
    ->amountType('amountType0')
    ->amount('amount0')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

