
# Purchase Options

*This model accepts additional fields of type array.*

## Structure

`PurchaseOptions`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `isElectronicBenefitsTransfer` | `?bool` | Optional | Flag that indicates whether this transaction is an EBT transaction. Possible values:<br><br>- `true`<br>- `false`<br><br>#### PIN debit<br><br>Required field for EBT and EBT voucher transactions that use PIN debit credit or PIN debit purchase; otherwise, not used. | getIsElectronicBenefitsTransfer(): ?bool | setIsElectronicBenefitsTransfer(?bool isElectronicBenefitsTransfer): void |
| `type` | `?string` | Optional | Flag that indicates an EBT voucher transaction. Possible value:<br><br>- `EBT_VOUCHER`: Indicates the PIN debit transaction is an EBT voucher.<br>- `BUY`<br>- `RENT`<br>- `BOOK`<br>- `SUBSCRIBE`<br>- `DOWNLOAD`<br>- `ORDER`<br>- `CONTINUE`<br><br>#### PIN debit<br><br>Required field for EBT voucher transactions that use PIN debit purchase; otherwise, not used.<br><br>**Constraints**: *Maximum Length*: `20` | getType(): ?string | setType(?string type): void |
| `eligibilityIndicator` | `?string` | Optional | This field contains installment data defined by MasterCard.<br>Possible values:<br><br>- Y = eligible<br>- N = not eligile<br><br>**Constraints**: *Maximum Length*: `20` | getEligibilityIndicator(): ?string | setEligibilityIndicator(?string eligibilityIndicator): void |
| `benefitAmount` | `?string` | Optional | Workplace benefit amount.<br><br>**Constraints**: *Maximum Length*: `20` | getBenefitAmount(): ?string | setBenefitAmount(?string benefitAmount): void |
| `benefitType` | `?string` | Optional | Workplace benefit type.<br>Possible values:<br><br>- 70 = employee benefit<br>- 4T = transportation / transit<br>- 52 = general benefit<br>- 53 = meal voucher<br>- 54 = fuel<br>- 55 = ecological / sustainability<br>- 58 = philanthropy / patronage / consumption<br>- 59 = gift<br>- 5S = sport / culture<br>- 5T = book / education<br><br>**Constraints**: *Maximum Length*: `100` | getBenefitType(): ?string | setBenefitType(?string benefitType): void |
| `additionalProperties` | `array<string, array>` | Optional | - | findAdditionalProperty(string key): array | additionalProperty(string key, array value): void |

## Example

```php
use VisaAcceptanceMergedSpecLib\Models\Builders\PurchaseOptionsBuilder;
use VisaAcceptanceMergedSpecLib\ApiHelper;

$purchaseOptions = PurchaseOptionsBuilder::init()
    ->isElectronicBenefitsTransfer(false)
    ->type('type0')
    ->eligibilityIndicator('eligibilityIndicator8')
    ->benefitAmount('benefitAmount8')
    ->benefitType('benefitType8')
    ->additionalProperty('exampleAdditionalProperty', ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

