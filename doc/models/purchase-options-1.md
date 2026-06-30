
# Purchase Options 1

*This model accepts additional fields of type array.*

## Structure

`PurchaseOptions1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `eligibilityIndicator` | `?string` | Optional | This field contains installment data defined by MasterCard.<br>Possible values:<br><br>- Y = eligible<br>- N = not eligile<br><br>**Constraints**: *Maximum Length*: `20` | getEligibilityIndicator(): ?string | setEligibilityIndicator(?string eligibilityIndicator): void |
| `type` | `?string` | Optional | Data mapped received in response from MasterCard.<br>Possible values:<br><br>- 01 = Meal Voucher - Employee Nutrition Program<br>- 02 = Food Voucher - Employee Nutrition Program<br>- 03 = Culture Voucher - Worker's Culture Program<br>- 04 = Meal Voucher - Consolidation of Labor Laws<br>- 05 = Food Voucher - Consolidation of Labor Laws<br><br>**Constraints**: *Maximum Length*: `20` | getType(): ?string | setType(?string type): void |
| `benefitAmount` | `?string` | Optional | Workplace benefit amount.<br><br>**Constraints**: *Maximum Length*: `20` | getBenefitAmount(): ?string | setBenefitAmount(?string benefitAmount): void |
| `benefitType` | `?string` | Optional | Workplace benefit type.<br>Possible values:<br><br>- 70 = employee benefit<br>- 4T = transportation / transit<br>- 52 = general benefit<br>- 53 = meal voucher<br>- 54 = fuel<br>- 55 = ecological / sustainability<br>- 58 = philanthropy / patronage / consumption<br>- 59 = gift<br>- 5S = sport / culture<br>- 5T = book / education<br><br>**Constraints**: *Maximum Length*: `100` | getBenefitType(): ?string | setBenefitType(?string benefitType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PurchaseOptions1Builder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$purchaseOptions1 = PurchaseOptions1Builder::init()
    ->eligibilityIndicator('eligibilityIndicator8')
    ->type('type0')
    ->benefitAmount('benefitAmount8')
    ->benefitType('benefitType8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

